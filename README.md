# Fast Debate Paste (v1.4)

## Overview

This utility copies text from a source window and pastes it into a card processing document. 

## Features

1. Persistent target window selection
2. Text processing for specific patterns, including figure/table/equation omissions
3. Customizable hotkeys via INI file
4. Toggle emphasis style for omissions (useful if you want to prevent your omissions from being shrunk)
5. An undo function
6. Built-in help dialogue
7. In Zotero, quick copying for debate citations

## Installation

1. Download the executable file.
2. Place the file in a convenient location on your computer.
3. Run the executable to start the program.
4. On first run, the program will create a Hotkeys.ini file in the same directory.

### Zotero and Zutilo Setup (Optional)

If you are using Zotero for managing debate cards and wish to automate the process of copying information into your card processing document, you must install the [Zutilo extension](https://github.com/wshanks/Zutilo/releases) for Zotero and configure it for seamless operation:

1. **Install Zutilo**: Download and install the Zutilo extension from the [GitHub releases page](https://github.com/wshanks/Zutilo/releases).
2. **Configure QuickCopy in Zutilo**: After installing Zutilo, open Zotero and go to the Zutilo preferences. Configure "QuickCopy items" to be activated with the `Ctrl + 0` hotkey.
3. **Set QuickCopy Output in Zotero Preferences**: 
   - Go to Zotero preferences and navigate to `Advanced -> Config Editor`.
   - Change the value of `extensions.zotero.export.quickCopy.setting` to match the output format you want to copy. If you're using Truf's custom Zotero style for policy debate, you would set the value to `bibliography=http://www.zotero.org/styles/policy-debate-v3`. Otherwise, you can find the URL by going to Zotero Preferences, selecting your preferred style, choosing Style Editor, and finding the url in the <id> field. Your value would then be `bibliography=yourIdFieldValue`. 

## Usage

### Initial Setup

When you run the program for the first time, it will create a Hotkeys.ini file with default settings and prompt you to select a target window.

### Default Hotkeys

The program uses the following default hotkeys:

1. `Ctrl+Shift+W`: Opens a window selection dialog to change the target window.
2. `Ctrl+Shift+C`: Performs the copy-process-paste operation.
3. `Ctrl+Shift+Z`: Performs the undo operation.
4. `Ctrl+Shift+H`: Displays the help dialogue.

### Customizing Hotkeys and Settings

You can customize hotkeys and settings by editing the Hotkeys.ini file:

1. Open the Hotkeys.ini file in a text editor.
2. Modify the values in the [Hotkeys] section to change hotkey assignments.
3. In the [Settings] section, set `ApplyF10ToProcessedText=1` to enable the F10 action, or `0` to disable it.

### Workflow

1. Run the executable.
2. Select your initial target window from the popup dialog.
3. Go to the source window and select the text you want to copy and process.
4. Press the copy-paste hotkey (default: `Ctrl+Shift+C`).
5. The program will copy the selected text, process it if it matches specific patterns, switch to the target window, paste the processed text, and (if the active window was not Zotero) switch back to the source window.

### Zotero Workflow

When using Zotero with Zutilo configured:

1. Select the Zotero items you want to copy. Ensure that Zotero is your active window. 
2. Press `Ctrl+Shift+C` to perform the Zotero Quick Copy function and paste it to your target window. The program will not switch back to Zotero after pasting.

### Changing the Target Window

If you need to change the target window at any time:

1. Press the change target window hotkey (default: `Ctrl+Shift+W`).
2. Select the new target window from the popup dialog.
3. Click OK.

### Using the Help Function

To access the built-in help:

1. Press the help hotkey (default: `Ctrl+Shift+H`).
2. A dialogue will appear with information about current hotkeys, rebinding instructions, current settings, and function explanations.

## Omissions

The program will attempt to catch and reformat elements you intend to indicate are omitted:
- If the copied text matches the pattern "WORD NUMBER" or "ABBREVIATED_WORD. NUMBER" (e.g., "Figure 2.1", "Fig. 2.1", or "Table 3.2.1"), it will be transformed to "[WORD NUMBER OMITTED]" or "[ABBREVIATED_WORD. NUMBER OMITTED]" in all caps.
- If the copied text is a standalone number (e.g., "3.1" or "2.43.45"), it will be transformed to "[EQUATION X OMITTED]" where X is the original number.
- The text processing is case-insensitive.
- If the text doesn't match these patterns, it will be pasted as-is.

## Error Handling

- If you try to use the copy-paste hotkey without selecting a target window, you'll be prompted to select one.
- If the target window is no longer available when you try to paste, you'll be notified and asked to select a new target window.
- If the program fails to copy text to the clipboard, you'll receive an error message and be asked to try again.

## Troubleshooting

- If hotkeys don't work, check for conflicts with other applications.
- If hotkeys are not working as expected, check the Hotkeys.ini file to ensure it's correctly configured.
- For issues with the F10 action, verify the `ApplyF10ToProcessedText` setting in the Hotkeys.ini file.
- If text isn't being processed as expected, the program will make multiple attempts to process it. In rare cases where processing still fails, the original text will be pasted unchanged.
- If you consistently experience issues with text processing, try selecting the text again and re-copying, as this can sometimes resolve clipboard-related issues.
- Ensure Zutilo is configured correctly and that Zotero is set up to use the correct output format in the `Config Editor`.
- For any other issues, try restarting the program or rebooting your computer.
- Ensure the program is running with appropriate permissions.

## Support

For support, please contact the program developer or refer to any provided support channels.

Remember to always back up your work and use this utility responsibly.
