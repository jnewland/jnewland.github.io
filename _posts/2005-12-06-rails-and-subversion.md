---

layout: post
typo_id: 127
title: Rails and Subversion
---
Woah, I missed the addition of the `-c` flag to the `./script/generate`
command. (When did this happen?) From the help:

<code>

    -c, --svn    Modify files with subversion. (Note: svn must be in path)

</code>

Let's try it:

<code>

    jnewland@slash trunk $ ./script/generate controller dashboard -c
          exists  app/controllers/
          exists  app/helpers/
          create  app/views/dashboard
    A         app/views/dashboard
          exists  test/functional/
          create  app/controllers/dashboard_controller.rb
    A         app/controllers/dashboard_controller.rb
          create  test/functional/dashboard_controller_test.rb
    A         test/functional/dashboard_controller_test.rb
          create  app/helpers/dashboard_helper.rb
    A         app/helpers/dashboard_helper.rb

</code>

Whoo! No more need to run `svn --force add .` or anything else after
generating a model, controller, or anything. There hasn't been a day in
months where I haven't found out something like this in rails - a small
touch that saves a big headache on my part. Nice work, guys :).
