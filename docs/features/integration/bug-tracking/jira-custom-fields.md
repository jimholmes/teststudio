---
title: Jira Custom Fields
page_title: How to Submit a Bug to Jira with Required Custom Field
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# How to Submit a Bug to Jira with Required Custom Field

The current Test Studio implementation for JIRA bug tracking does not support specifying custom fields through the UI when submitting a bug. Thus you will get the following error when try to submit the bug directly:

![Jira Error][1]

In order to denote your required fields and what to fill them with, create a file called **JiraMappings.json** in the following directory: **C:\Program Files (x86)\Telerik\Test Studio\Bin\Plugins**

![Plugins Folder][2]

> Please note that as of version **2017 R3 2017.3.1010** the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

Open it with a text editor, like Notepad, and insert the following content:

```json
{
"IssueTypeName": "Defect",
"Fields" : {"assignee": {"name": "username" }, "labels": ["defect"],  "customfield_10401":{"required custom field": "value"}, "customfield_10402":{"another required custom field": "value"} }
}
```

In JIRA, custom fields are referenced by "customfield_" + the id of the custom field. In the above example there are two custom fields referrenced with their names and respective values. 

> When configuring the default values for your custom fields in the json file, you should have in mind the type of the field and use the correct id and syntax.
> 
> <a href="https://developer.atlassian.com/display/JIRADEV/JIRA+REST+API+Example+-+Create+Issue#JIRARESTAPIExample-CreateIssue-Examplesofhowtosetcustomfielddataforotherfieldtypes:" target="_blank">**Here are**</a> some examples of how to set different types of custom fields.

[1]: /img/features/integration/bug-tracking/jira-custom-fields/fig1.png
[2]: /img/features/integration/bug-tracking/jira-custom-fields/fig2.png