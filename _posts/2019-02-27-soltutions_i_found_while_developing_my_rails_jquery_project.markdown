---
layout: post
title:      "Soltutions I Found While Developing My Rails/jQuery Project"
date:       2019-02-27 13:31:55 -0500
permalink:  soltutions_i_found_while_developing_my_rails_jquery_project
---


I have now finished development of my Rails with jQuery project. Here's what I found.

My first issue was that none of my JavaScript was being used. I would quickly find out that the CoffeeScript files take precedence over JavaScript files, so I needed to either rename my JavaScript files, or delete the CoffeeScript files. Because I wasn't planning touse CoffeeScript, I chose to delete those files.

Later in the proiect, I would want to find a way to limit the JavaScript to specific views. There is a 3-step process to do this easily. First, add `//= stub 'file_name.js` to the `application.js` file. Next, add `Rails.application.config.assets.precompile += %w( file_name.js )` to `assets.rb` in the initializers folder in the config folder. Finally, add a JavaScript include tag `<%= javascript_include_tag 'file_name' %>` to the desired views.

The last thing I fixed was `setInterval()`. In my project, I wanted to run a piece of code after a set interval. But `setInterval() ` waits the interval length when it is first invoked. This means that I would have to wait 10 second from invoking it to running the code. Instead I built setIntervalImmediately() which is a simple function that runs the function and then sets the interval to run it again.

`function setIntervalImmediately(func, interval) {
  func();
  return setInterval(function, interval);
}`

You can check out my project [here](https://github.com/E-Shiels/appointments). I hope this helps you build your project. Thanks for reading!
