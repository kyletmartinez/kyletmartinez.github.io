---
layout: default
title: Debugging Cyclops
permalink: /cyclops/support/debugging-cyclops/
nav_order: 1
parent: Support
---

# Debugging Cyclops

In extreme cases, I may need more information about Cyclops’ behavior on your computer. Please follow these debugging steps so I can pinpoint the issue and hopefully resolve it quickly.

{: .warning }
> To complete the debugging process, you’ll need [Google Chrome](https://www.google.com/chrome/) installed on your computer.

## View Debugging Info
1. Open **After Effects**.
2. Open Cyclops from the **Window** > **Extensions** > **Cyclops** menu.
3. Open your **Chrome** web browser.
4. In the address bar, type `localhost:8092`.
5. Under **Inspectable WebContents**, click the link to **panel.html** to open a new window.
6. Click the menu icon (three dots) in the top right of Chrome and navigate to **More Tools** > **Developer Tools**.
7. In the top left of the new window, click **Console** to open the JavaScript console.

## Send Debugging Info
1. Attempt another Cyclops render. It may fail, but that’s okay for now.
2. Go back to Chrome and take a screenshot of the page. You’ll likely see red text.
3. Send that screenshot via the [aescripts + aeplugins contact form](https://aescripts.com/contact/?product_id=2470).

{: .note }
> Special thanks to Olivia G. and James R. for helping me smooth out the instructions for this process!