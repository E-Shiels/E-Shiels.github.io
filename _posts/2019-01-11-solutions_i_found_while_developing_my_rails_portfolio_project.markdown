---
layout: post
title:      "Solutions I Found While I Developed My Rails Portfolio Project"
date:       2019-01-11 15:51:11 -0500
permalink:  solutions_i_found_while_developing_my_rails_portfolio_project
---

My Rails Portfolio project is called Appointments. You can check out the GitHub repository [here.](https://github.com/E-Shiels/appointments)

It allows Doctors and Patients to view and create appointments. It's not the most useful application, as it is lacking many features that such a platform should have, but I thought that it would be a good way to demonstrate Rails fundamentals.

While developing this program, I ran into two major problems. And hopefully, showing you the solutions/workarounds I found will help you develop your Rails project.

The first problem I ran into was that error fields were messing up the design of my website. The design of the site wasn't incredible, but the errors would completely change the location of the input labels. This is because, by default, Rails wraps the label and input in separate `divs`. Those `divs` are block-style elements, which causes the elements inside them to change location. I found [this solution](https://stackoverflow.com/questions/5267998/rails-3-field-with-errors-wrapper-changes-the-page-appearance-how-to-avoid-t) which uses an initializer to tag elements with errors with a tag of `class="error"` instead of using `divs`. I just needed to apply some extra styling, and those errors were displaying nicely.

The second problem I ran into was with SSL certificate verification. 3rd-party authentication (with GitHub) requires you to use an SSL certificate, and no matter how hard I tried, and how long I Googled, I couldn't find a solution. So, I decided to bypass it entirely with this line of code I placed into the `application.rb` file: `OpenSSL::SSL::VERIFY_PEER = OpenSSL::SSL::VERIFY_NONE`. I think I found that solution [here.](https://stackoverflow.com/questions/1113422/how-to-bypass-ssl-certificate-verification-in-open-uri) It tells OpenSSL to not verify that a certificate exists. This is VERY DANGEROUS and should not be used in production, but it works fine for testing.

I hope that these solutions will help you as you build your Rails project. Thanks for reading.
