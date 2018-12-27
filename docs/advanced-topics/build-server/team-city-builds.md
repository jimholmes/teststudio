---
title: TeamCity Builds
page_title: TeamCity Test Execution
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/command-line-test-execution/continuous-integration/teamcity.aspx, /user-guide/command-line-test-execution/continuous-integration/teamcity
position: 2
---
# TeamCity Test Execution #

## TeamCity installation ##

There are no specifics in installation of the TeamCity server. To be able to execute automated tests that include Windows and Browser interactions it is necessary to run build agent from command line.

## Run the build agent ##

The build agent **have** to be started in a **console mode**. To complete that follow these steps:

1.&nbsp; Locate the build agent's bin folder. The default is C:\TeamCity\buildAgent\bin.

2.&nbsp; Open a command prompt window.

3.&nbsp; Change to the bin folder you just located.

4.&nbsp; Enter 'agent start'. 

## Configure TeamCity project ##

1.&nbsp; Create new project

![Create new project][1]

2.&nbsp; Create new build configuration:

![Create new build config][2]

3.&nbsp; Add new command line build step

![New build step][3]

For "Build script content" enter:
"PATH_TO_TEST_STUDIO_BIN_DIR\ArtOfTest.Runner.exe" test="C:\Users\deyan\Desktop\TestStudio\WebTest.tstest" out="C:\Users\deyan\Desktop\TestStudioResults" junitstep

Path to Test Studio runner

```
list="PATH_TO_PROJECT\TEST_LIST_NAME.aiilist" out="PATH_TO_RESULT_DIR"  junitstep
```

**OR**

```
test="PATH_TO_PROJECT\TEST_NAME.tstest" out="PATH_TO_RESULT_DIR" junitstep
```

4.&nbsp; Add new Build Feature

![New Build Feature][4]

From drop-down list, select "XML report processing"

For report type select "Ant JUnit" and save build feature.

For "Monitoring rules" specify output directory from previous step and ad all xml files.

Example: 
	C:\Users\deyan\Desktop\TestStudioResults\*.xml
 
[1]: /img/advanced-topics/build-server/team-city-builds/New_project.png
[2]: /img/advanced-topics/build-server/team-city-builds/New_Build_config.png
[3]: /img/advanced-topics/build-server/team-city-builds/New_build_step.png
[4]: /img/advanced-topics/build-server/team-city-builds/New_Build_Feature.png