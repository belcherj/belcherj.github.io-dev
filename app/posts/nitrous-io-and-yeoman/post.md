I have been a little work on Nitrous.io a service that lets you create a full
Dev Environment in the cloud in less than 60 seconds.
https://www.nitrous.io/join/8QIWJcTk6gU (Shameless invite link)

I setup a box with Node as advertised very quickly and can now access and code
on that box from any computer with an Internet connection.

I found getting Yeoman up and running a little more tricky.  The livereload in
the packaged Grunt server does not work on Nitrous and required some
modification.

I am using generator-angular in this case but I have managed to use this same
method with generator-mobile.

https://github.com/yeoman/generator-angular/blob/master/templates/common/Gruntfile.js

Install everything like you normally would. `yo angular [app-name]`

Then open up your Gruntfile.js.  Your need to change every instance of
`localhost` to `0.0.0.0`.

Remove `lrSnippet,` from line 78 (subject to change).

That will keep Grunt server from running livereload.  You also may want to
change the port numbers to use the quick links that Nitrous uses (3000, 4000,
8080 or 8888)

You should now be able to use Grunt server and preview your application.  

Next up:  How I am using this frontend with the Node/Express API.
