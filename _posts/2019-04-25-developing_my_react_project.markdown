---
layout: post
title:      "Developing My React Project"
date:       2019-04-25 19:25:29 +0000
permalink:  developing_my_react_project
---


I just finished development of my React/Redux project. I started working on it on March 19th and today is April 25th, so it definitely took a while. This project was very challenging, but also very rewarding.

My project is called[ HolidayFinder](https://github.com/E-Shiels/HolidaysFinder). It allows you to search and filter Canadian holidays, as well as mark your favorites.

![](https://i.ibb.co/PFF7XG6/Holidays-Finder1.png)

In this post, I want to walk through parts of my process in developing this application and provide some tips for future students working on this project.

I started this project the way I started all of the other projects. Planning, and then stubbing out most of the files I thought I would need. I found somewhere to get the holiday data from, and started off by putting it into a local JSON file, which I could seed the database from. This can save you time inthe beginning because you can work on the meat of the project, without having to worry about connecting your React app to your Rails API. 

Next, I started building the static parts of the website; an about page, the Navbar, and the footer. Then came the hard parts. I had used React about 3 years ago, so that part came relatively easy, (and I was very happy to see that ES6 meant that we didn't have to bind `this` over and over,) but Redux felt very different compared to normal React state management. And because I wanted to use a few ready-made elements for filtering and for the date-picker, I decided to use a more local react state than normal for controlled forms. This mean that I could't easily do any on-the-fly input validation, but I hadn't planned to use much validation, so this wasn't too much of a concern.

This part of the development was a bit of a slog. I worked on the React components and connecting them to the Redux store for the vast majority of the time I spent on this project. Nothing veryeventful happened during this time, just a slow grind towards completion.

Once everything was working, it was time to work on the visuals. I decided to use MaterialUI. This was a mistake. I highly recommend not to use it with Redux, as theydo not play well together. There is a MateriaUI method called withStyles() thatallows you to export a component with styles you define on top of the defaults. However, it doesn't work well with exporting connected components which need a connect() statement. I recommend that you either hand-style your project or use Semantic UI. Hand-styling is an important skill, that I feel is often overlooked. Ihad hand-styled my previous projects, and wanted to show that I could implement a visual library.As i said before, this was a mistake.


Here are some recommendations for a few packages that I found useful:
* [Fast Deep Equal](https://github.com/epoberezkin/fast-deep-equal) is the best way to compare data inside componentDidUpdate
* [uuid](https://github.com/kelektiv/node-uuid) allows you to generate random keys as required by React for elements without pre-generated IDs
* [email-validator](https://github.com/manishsaraan/email-validator) is, as described in its Github repo, a 'fast and pretty robust' way to validate that an email is in valid format

I also want to recommend using a code quality tool suchas Code Climate, Codacy, or Codebeat. They will scan your repository for code issues such as duplicated code, overly complex loops, or syntax errors that may not have been picked up by your editor.

Thanks you for reading. You can check out the Github repository [here](https://github.com/E-Shiels/HolidaysFinder).


