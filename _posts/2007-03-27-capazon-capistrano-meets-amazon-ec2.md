---

layout: post
typo_id: 3644
title: Capazon - Capistrano Meets Amazon EC2
---
**UPDATE**: For those looking for [Capistrano
2.0](http://www.capify.org/) support, check out [Capazon
0.2.0](http://soylentfoo.jnewland.com/articles/2007/04/30/capazon-0-2-released-capistrano-2-0-compatible)

Just a quick note to announce [Capazon](http://capazon.rubyforge.org/)
[0.1.0](http://rubyforge.org/frs/?group_id=3073&release_id=10690), a
[Capistrano](http://manuals.rubyonrails.com/read/book/17) extension
library to manage [Amazon EC2](http://aws.amazon.com/ec2) instances. If
you are familiar with Capistrano and have an Amazon EC2 account, give it
a whirl:

-   `gem install capazon`
-   Edit your your `config/deploy.rb`:

{% highlight ruby %}
require 'capazon'

\#AWS login info
set :aws_access_key_id, 'XXX'
set :aws_secret_access_key, 'X'

1.  Name of the keypair used to spawn and connect to the Amazon EC2
    Instance
2.  Defaults to one created by the setup_keypair task
    set :aws_keypair_name, "\#{application}-capazon"

<!-- -->

1.  Path to the private key for the Amazon EC2 Instance mentioned above
2.  Detaults to one created by setup_keypair task
    set :aws_private_key_path,
    "\#{Dir.pwd}/\#{aws_keypair_name}-key"

\#defaults to an ubuntu image
\#set :aws_ami_id, "ami-e4b6538d"

\#defaults to, um, default
\#set :aws_security_group, "default"
{% endhighlight %}

-   `$ cap describe_images`

{% highlight text %}
\* executing task describe_images
IMAGE ami-0386636a
rbuilder-online/nuxleus-1.3-x86_9327.img.manifest.xml 099034111737
available true
IMAGE ami-08866361 rbuilder-online/test1-1.0-x86_9326.img.manifest.xml
099034111737 available true
IMAGE ami-1281647b
rbuilder-online/mw-tour-1.6.8-x86_9458.img.manifest.xml 099034111737
available true
IMAGE ami-1681647f
rbuilder-online/mw-tour-1.6.8-x86_9459.img.manifest.xml 099034111737
available true
{% endhighlight %}

-   `$ AWS_AMI_ID=XXXX cap run_instance`

This release just scratches the surface of what I hope to accomplish
with Capazon - my end goal is to provide a shared AMI as a companion to
Capazon which will encapsulate some Rails deployment best practices.

Please [report any
bugs](http://rubyforge.org/tracker/?func=add&group_id=3073&atid=11863)
you may come across, and stay tuned for updates!
