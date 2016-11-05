------------------------------------------------------------------------

layout: post\
typo\_id: 3841\
title: resource\_this - DRY Rails Resource Controllers\
---\

&lt;div style="float:left;margin:10px;"&gt;
&lt;script type="text/javascript"&gt;&lt;!--
google\_ad\_client = "pub-5165033129816339";
//250x250, created 11/22/07
google\_ad\_slot = "4463239324";
google\_ad\_width = 250;
google\_ad\_height = 250;
//--&gt;&lt;/script&gt;
&lt;script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show\_ads.js"&gt;
&lt;/script&gt;
&lt;/div&gt;

I've always been annoyed at the lack of maintainability that comes with
using multiple resource controllers in my Rails apps. Each generated
resource controller clocks in at 85 lines, and most of mine only differ
from each other by a line or two - an added `before_filter` or a change
in the url that the users is redirected to after the creation of a new
Widget. Not very
[DRY](http://en.wikipedia.org/wiki/Don%27t_repeat_yourself). When coming
back to each one of these controllers to add or adjust features, it
takes me entirely too much time to sift through the stock 85 lines and
find my application-specific behavior.

### Enter resource\_this

{% highlight text %}\
git clone git://github.com/jnewland/resource\_this.git\
{% endhighlight %}

[**resource\_this**](http://github.com/jnewland/resource_this/tree/master)
aims to solve this maintainability problem by making your stock resource
controllers look like this:

{% highlight ruby %}\
class PostsController &lt; ActionController::Base\
resource\_this\
end\
{% endhighlight %}

Behind the scenes, this code is generated:

{% highlight ruby %}\
class PostsController &lt; ActionController::Base\
before\_filter :load\_post, :only =&gt; \[ :show, :edit, :update,
:destroy \]\
before\_filter :load\_posts, :only =&gt; \[ :index \]\
before\_filter :new\_post, :only =&gt; \[ :new \]\
before\_filter :create\_post, :only =&gt; \[ :create \]\
before\_filter :update\_post, :only =&gt; \[ :update \]\
before\_filter :destroy\_post, :only =&gt; \[ :destroy \]

protected\
def load\_post\
@post = Post.find(params\[:id\])\
end

def new\_post\
@post = Post.new\
end

def create\_post\
`post = Post.new(params[:post])
      `created = @post.save\
end

def update\_post\
`updated = `post.update\_attributes(params\[:post\])\
end

def destroy\_post\
`post = `post.destroy\
end

def load\_posts\
@posts = Post.find(:all)\
end

public\
def index\
respond\_to do |format|\
format.html\
format.xml { render :xml =&gt; @posts }\
format.js\
end\
end

def show\
respond\_to do |format|\
format.html\
format.xml { render :xml =&gt; @post }\
format.js\
end\
end

def new\
respond\_to do |format|\
format.html { render :action =&gt; :edit }\
format.xml { render :xml =&gt; @post }\
format.js\
end\
end

def create\
respond\_to do |format|\
if `created
          flash[:notice] = 'Post was successfully created.'
          format.html { redirect_to `post }\
format.xml { render :xml =&gt;
`post, :status => :created, :location => `post }\
format.js\
else\
format.html { render :action =&gt; :new }\
format.xml { render :xml =&gt; @post.errors, :status =&gt;
:unprocessable\_entity }\
format.js\
end\
end\
end

def edit\
respond\_to do |format|\
format.html\
format.js\
end\
end

def update\
respond\_to do |format|\
if `updated
          flash[:notice] = 'Post was successfully updated.'
          format.html { redirect_to `post }\
format.xml { head :ok }\
format.js\
else\
format.html { render :action =&gt; :edit }\
format.xml { render :xml =&gt; @post.errors, :status =&gt;
:unprocessable\_entity }\
format.js\
end\
end\
end

def destroy\
respond\_to do |format|\
format.html { redirect\_to :action =&gt; posts\_url }\
format.xml { head :ok }\
format.js\
end\
end\
end\
{% endhighlight %}

Nested resources like so:

{% highlight ruby %}\
class CommentsController &lt; ActionController::Base\
resource\_this :nested =&gt; \[:posts\]\
end\
{% endhighlight %}

This generates a very similar controller to the one above with adjusted
redirects and one additional before\_filter / loader method pair to grab
the parent resource. In this case:

{% highlight ruby %}\
before\_filter :load\_post

def load\_post\
@post = Post.find(params\[:post\_id\])\
end\
{% endhighlight %}

The separation of logic - DB operations in before\_filters, rendering in
the standard resource controller methods - makes this approach
ridiculously easy to customize. Need to load an additional object for
the `:show` action? Slap another before\_filter on it. Need to change
the path that the `:update` action redirects to? Override the `:update`
action with your new rendering behavior. And this customized behavior
sticks out like a sore thumb - making it infinitely easier to maintain.

Oh, there's also a generator:

{% highlight text %}\
./script/generate resource\_this FooKlass \[title:string body:text\]\
{% endhighlight %}

This works just like the `resource` generator, with the addition of the
`resource_this` line to your controller and a functional test. No views
are generated, so the test focuses on the XML behavior of this
controller.

### Contributing

[resource\_this](http://github.com/jnewland/resource_this/tree/master)
is hosted on [GitHub](http://github.com), so feel free to fork it and
send a [pull request](http://github.com/guides/pull-requests) with your
changes.
