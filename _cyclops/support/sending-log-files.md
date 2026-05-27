---
layout: default
title: Sending Log Files
permalink: /cyclops/support/sending-log-files/
nav_order: 2
parent: Support
---

# Sending Log Files

If you are unable to find a solution using this help documentation and you reach out to me for assistance I may ask you to enable logging, try a render, and send me the files found in the log folder.

Log files contain helpful information about the attempted render and help me diagnose and fix the problem.

## Enable Logging
1. In the Cyclops panel, click the **Settings** button to open the **Cyclops Settings** window.
2. Check the **Enable logging** checkbox.
3. Click the **Okay** button to close the **Cyclops Settings** window and save the new settings.

{: .warning }
> Cyclops will continue to log every render and create log files each time until you disable this setting

## Revealing Log Files

### macOS

1. Press `Shift + Command + G` or click **Go** then **Go to Folder...** in the Menu Bar
2. Enter the following folder to open a Finder window and reveal the log files:
    - `~/Library/Application Support/Cyclops`

### Windows

1. Press `Win + R` or right-click the **Start** button and select **Run**
2. Enter the following path and press Enter to open a File Explorer window and reveal the log files:
    - `%APPDATA%\Cyclops`

## Sending Log Files

1. Log files should appear as a collection of files: a single JSON file and at least one or more PNG files all prefixed with the same 13 random numbers. For example:
    - `1779211488316`.json
    - `1779211488316`-12763.png
    - `1779211488316`-12862.png
2. When sending log files via the [aescripts + aeplugins contact form](https://aescripts.com/contact/?product_id=2470) you’ll need to compress all files into a ZIP archive because you are unable to attach JSON files to support messages.