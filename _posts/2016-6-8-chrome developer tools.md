---
layout:  post
title :  chromeDeveloperTools
---

## Chrome DevTools Overview

The Chrome Developer Tools (DevTools for short), are a set of web authoring and debugging tools built into Google Chrome. The DevTools provide web developers deep access into the internals of the browser and their web application. Use the DevTools to efficiently track down layout issues, set JavaScript breakpoints, and get insights for code optimization.

The DevTools docs have moved!For the latest tutorials, docs and updates [head over to the new home of Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools).

### Accessing the DevTools

To access the DevTools, open a web page or web app in Google Chrome. Either:

- Select the **Chrome menu** ![Chrome Menu](https://developer.chrome.com/devtools/images/chrome-menu.png) at the top-right of your browser window, then select **Tools** &gt; **Developer Tools**.
- Right-click on any page element and select **Inspect Element**.

The DevTools window will open at the bottom of your Chrome browser.

There are several useful shortcuts for opening the DevTools:

- Use 

Ctrl+

Shift+

I (or 

Cmd+

Opt+

I on Mac) to open the DevTools.
- Use 

Ctrl+

Shift+

J (or 

Cmd+

Opt+

J on Mac) to open the DevTools and bring focus to the Console.
- Use 

Ctrl+

Shift+

C (or 

Cmd+

Shift+

C on Mac) to open the DevTools in Inspect Element mode, or toggle Inspect Element mode if the DevTools are already open.

For your day-to-day workflow, [learning the shortcuts](https://developer.chrome.com/devtools/docs/shortcuts) will save you time.

### The DevTools window

The DevTools are organised into task-oriented groups in the toolbar at the top of the window. Each toolbar item and corresponding panel let you work with a specific type of page or app information, including 

DOMelements, resources, and sources.

![Image](https://developer.chrome.com/devtools/images/devtools-window.png)

The colorpicker available in the DevTools..

Overall, there are eight main groups of tools available view Developer Tools:

- [Elements](https://developer.chrome.com/devtools/docs/dom-and-styles)
- [Resources](https://developer.chrome.com/devtools/docs/resource-panel)
- [Network](https://developer.chrome.com/devtools/docs/network)
- Sources
- [Timeline](https://developer.chrome.com/devtools/docs/timeline)
- [Profiles](https://developer.chrome.com/devtools/docs/profiles)
- Audits
- [Console](https://developer.chrome.com/devtools/docs/console)

You can use the 

Ctrl+

[ and 

Ctrl+

] shortcuts to move between panels.

### Inspecting the DOM and styles

The **[Elements](https://developer.chrome.com/devtools/docs/dom-and-styles)** panel lets you see everything in one DOM tree, and allows inspection and on-the-fly editing of DOM elements. You will often visit the Elements tabs when you need to identify the 

HTML snippet for some aspect of the page. For example, you may be curious if an image has an HTML id attribute and what the value is.

![Image](https://developer.chrome.com/devtools/images/elements-panel.png)

Viewing a heading element in the DOM.

[Read more about inspecting the DOM and styles](https://developer.chrome.com/devtools/docs/dom-and-styles)

### Working with the Console

The [JavaScript Console](https://developer.chrome.com/devtools/docs/console) provides two primary functions for developers testing web pages and applications. It is a place to:

- Log diagnostic information in the development process.
- A shell prompt which can be used to interact with the document and DevTools.

You may log diagnostic information using methods provided by the [Console 

API](https://developer.chrome.com/devtools/docs/console-api). Such as [console.log()](https://developer.chrome.com/devtools/docs/console-api#consolelogobject-object) or[console.profile()](https://developer.chrome.com/devtools/docs/console-api#consoleprofilelabel).

You can evaluate expressions directly in the console and use the methods provided by the [Command Line API](https://developer.chrome.com/devtools/docs/commandline-api). These include [$()](https://developer.chrome.com/devtools/docs/commandline-api#selector) command for selecting elements or [profile()](https://developer.chrome.com/devtools/docs/commandline-api#profilename) to start the 

CPU profiler.

![Image](https://developer.chrome.com/devtools/docs/console-files/expression-evaluation.png)

Evaluating some commands in the 

JS Console.

[Read more about working with the console](https://developer.chrome.com/devtools/docs/console)

### Debugging JavaScript

As the **complexity** of JavaScript applications increase, developers need powerful debugging tools to help quickly discover the cause of an issue and fix it efficiently. The Chrome DevTools include a number of useful tools to help make **debugging** JavaScript less painful.

![Image](https://developer.chrome.com/devtools/images/js-debugging.png)

A conditonal breakpoint which logs to the console.

[Read more about how to debug JavaScript with the DevTools »](https://developer.chrome.com/devtools/docs/javascript-debugging)

### Improving network performance

The **Network** panel provides insights into resources that are requested and downloaded over the network in real time. Identifying and addressing those requests taking longer than expected is an essential step in optimizing your page.

![Image](https://developer.chrome.com/devtools/images/network-panel.png)

The context menu for network requests.

[Read more about how to improve your network performance »](https://developer.chrome.com/devtools/docs/network)

### Audits

The Audit panel can analyze a page as it loads. Then provides suggestions and optimizations for decreasing page load time and increase perceived (and real) responsiveness. For further insight, we recommend using[PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/).

![Image](https://developer.chrome.com/devtools/images/audits-panel.png)

The recommendations of an audit.

### Improving rendering performance

The **Timeline** panel gives you a complete overview of where time is spent when loading and using your web app or page. All events, from loading resources to parsing JavaScript, calculating styles, and repainting are plotted on a timeline.

![Image](https://developer.chrome.com/devtools/images/timeline-panel.png)

An example timeline with various events.

[Read more about how to improve rendering performance »](https://developer.chrome.com/devtools/docs/timeline)

### JavaScript & 

CSS performance

The **Profiles** panel lets you profile the execution time and memory usage of a web app or page. These help you to understand where resources are being spent, and so help you to optimize your code. The provided profilers are:

- The **CPU profiler** shows where execution time is spent in your page's JavaScript functions.
- The **Heap profiler** shows memory distribution by your page's JavaScript objects and related DOM nodes.
- The **JavaScript** profile shows where execution time is spent in your scripts

![Image](https://developer.chrome.com/devtools/images/profiles-panel.png)

An example heap snapshot.

[Read more about using how to improve JavaScript and CSS performance »](https://developer.chrome.com/devtools/docs/profiles)

### Inspecting storage

The **Resources** panel lets you inspect resources that are loaded in the inspected page. It lets you interact with HTML5 Database, Local Storage, Cookies, AppCache, etc.

![Image](https://developer.chrome.com/devtools/images/resources-panel.png)

The JavaScript file of the [Web Starter Kit](https://developers.google.com/web/starter-kit/) as displayed in the resources panel.

[Read more about inspecting storage resources »](https://developer.chrome.com/devtools/docs/resource-panel)

### Further reading

There are several other areas of the DevTools documentation that you might find beneficial to review. These include:

- [Heap Profiling](https://developer.chrome.com/devtools/docs/heap-profiling)
- [CPU Profiling](https://developer.chrome.com/devtools/docs/cpu-profiling)
- [Device Mode & Mobile Emulation](https://developer.chrome.com/devtools/docs/device-mode)
- [Remote Debugging](https://developer.chrome.com/devtools/docs/remote-debugging)
- [DevTools Videos](https://developer.chrome.com/devtools/docs/videos)

### Further resources

#### Get more

You can also follow us on [@ChromiumDev](http://twitter.com/ChromiumDev) or ask a question using the [forums](https://groups.google.com/forum/?fromgroups#!forum/google-chrome-developer-tools).

![Image](https://developer.chrome.com/devtools/images/image13.png)

Styled output in the console.

Be sure to checkout the Google Chrome Developers page on [Google+](https://plus.google.com/+GoogleChromeDevelopers/posts).
