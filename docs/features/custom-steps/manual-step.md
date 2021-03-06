---
title: Manual Step
page_title: Manual Step
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 13
---
# Manual Step

This step will display directions for a manual step at a specific point in the test.

If, for some reason, a certain step cannot be automated and you wish you run it manually, simply add a Manual Step to your test. Enter directions for that step and Test Studio will prompt the tester to perform the action, and then choose to pass or fail that step. If fail is chosen, the tester can enter a comment on the reason.

![Manual Step](/img/features/custom-steps/manual-step/fig2.png)


![Manual Step](/img/features/custom-steps/manual-step/fig1.png)

A perfect use for a Manual Step is for sites that use a <a href="http://en.wikipedia.org/wiki/CAPTCHA" target="_blank">CAPTCHA</a> code. Test Studio does not support CAPTCHA automation as it cannot read the text contained within the CAPTCHA image. The tool was not designed to be used for such a purpose. In fact, CAPTCHA is specifically designed to ensure the response is generated by a person and not a computer.

We recommend using a Manual Step and have the tester type in the code.