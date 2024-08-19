# Fast Debate Paste (v1.3)

## Overview

This utility provides a convenient way to copy text from one window, process it, and paste it into a card processing document. It is optimized for quick copying and text transformation, making it especially useful for debate preparation.

## Features

1. Persistent target window selection
2. Text processing for specific patterns, including abbreviated words
3. Hotkeys for quick operation
4. Error handling for unavailable windows and clipboard operations
5. Improved timing and reliability for text processing operations
6. Retry mechanism for more consistent regex matching
7. Enhanced support for Zotero, including automatic text copying using the Zutilo extension

## Installation

1. Download the executable file.
2. Place the file in a convenient location on your computer.
3. Run the executable to start the program.

### Zotero and Zutilo Setup (Optional)

If you are using Zotero for managing debate cards and wish to automate the process of copying information into your card processing document, you must install the [Zutilo extension](https://github.com/wshanks/Zutilo/releases) for Zotero and configure it for seamless operation:

1. **Install Zutilo**: Download and install the Zutilo extension from the [GitHub releases page](https://github.com/wshanks/Zutilo/releases).
2. **Configure QuickCopy in Zutilo**: After installing Zutilo, open Zotero and go to the Zutilo preferences. Configure "QuickCopy items" to be activated with the `Ctrl + 0` hotkey.
3. **Set QuickCopy Output in Zotero Preferences**: 
   - Go to Zotero preferences and navigate to `Advanced -> Config Editor`.
   - Change the value of `extensions.zotero.export.quickCopy.setting` to match the output format you want to copy. If you're using Truf's custom Zotero style for policy debate, you would set the value to `bibliography=http://www.zotero.org/styles/policy-debate-v3`. Otherwise, you can find the URL by going to Zotero Preferences, selecting your preferred style, choosing Style Editor, and finding the url in the <id> field. Your value would then be `bibliography=yourIdFieldValue`. 

## Usage

### Initial Setup

When you run the program for the first time, it will prompt you to select a target window. This is the window where the processed text will be pasted.

### Hotkeys

The program uses two main hotkeys:

1. `Ctrl+Shift+W`: Opens a window selection dialog to change the target window.
2. `Ctrl+Shift+C`: Performs the copy-process-paste operation.

### Workflow

1. Run the executable.
2. Select your initial target window from the popup dialog.
3. Go to the source window and select the text you want to copy and process.
4. Press `Ctrl+Shift+C`.
5. The program will copy the selected text, process it if it matches a specific pattern, switch to the target window, paste the processed text, and (if the active window was not Zotero) switch back to the source window.

### Zotero Workflow

When using Zotero with Zutilo configured:

1. Select the Zotero items you want to copy.
3. Press `Ctrl+Shift+C` to perform the Zotero Quick Copy function and paste it to your target window. The program will not switch back to Zotero after pasting.

### Changing the Target Window

If you need to change the target window at any time:

1. Press `Ctrl+Shift+W`.
2. Select the new target window from the popup dialog.
3. Click OK.

## Text Processing

The program includes a text processing feature with improved reliability:

- If the copied text matches the pattern "WORD NUMBER" or "ABBREVIATED_WORD. NUMBER" (e.g., "Figure 2.1", "Fig. 2.1", or "Table 3.2.1"), it will be transformed to "[WORD NUMBER OMITTED]" or "[ABBREVIATED_WORD. NUMBER OMITTED]" in all caps.
- The text processing is case-insensitive, so "figure 2.1" and "FIGURE 2.1" will both be processed.
- If the text doesn't match this pattern, it will be pasted as-is.
- The program includes a retry mechanism that attempts to process the text multiple times if necessary, improving the consistency of the regex matching.

## Error Handling

- If you try to use `Ctrl+Shift+C` without selecting a target window, you'll be prompted to select one.
- If the target window is no longer available when you try to paste, you'll be notified and asked to select a new target window.
- If the program fails to copy text to the clipboard, you'll receive an error message and be asked to try again.

## Troubleshooting

- If hotkeys don't work, check for conflicts with other applications.
- If text isn't being processed as expected, the program will make multiple attempts to process it. In rare cases where processing still fails, the original text will be pasted unchanged.
- If you consistently experience issues with text processing, try selecting the text again and re-copying, as this can sometimes resolve clipboard-related issues.
- Ensure Zutilo is configured correctly and that Zotero is set up to use the correct output format in the `Config Editor`.
- For any other issues, try restarting the program or rebooting your computer.
- Ensure the program is running with appropriate permissions.

## Support

For support, please contact the program developer or refer to any provided support channels.

Remember to always back up your work and use this utility responsibly.

---

# Changelog

## v1.3
- **Added Zotero Integration**: Supports automatic copying of items in Zotero using the Zutilo extension. Users must configure Zutilo to use `Ctrl + 0` for QuickCopy.
- **Target Window Switching for Zotero**: The program now recognizes when Zotero is the active window and will not return to Zotero after pasting the processed text.
- **Documentation Update**: Added instructions for Zotero and Zutilo setup.

## v1.2

#### New Features and Improvements

1. **Enhanced Regex Processing**: Implemented a more robust regex matching system to handle a wider range of text patterns, including abbreviated words (e.g., "Fig." for "Figure").

2. **Retry Mechanism**: Added a retry mechanism for text processing. The program now attempts to process the text multiple times if the initial attempt fails, improving the consistency of regex matching.

3. **Improved Clipboard Handling**: Enhanced the clipboard operations with better timing and error checking to ensure more reliable text copying and pasting.

4. **Separated Text Processing Logic**: Moved text processing into separate functions (`ProcessText` and `ProcessTextWithRetry`) for better code organization and easier maintenance.

5. **Increased Wait Times**: Added and adjusted wait times at crucial points in the script to allow for more reliable window switching and text pasting.

6. **Improved Error Handling**: Enhanced error messages and handling for scenarios such as failed clipboard operations or unavailable target windows.

7. **Case-Insensitive Matching**: The regex pattern is now case-insensitive, allowing it to match text regardless of capitalization.

#### Bug Fixes

1. Fixed potential issues with window activation by implementing a more robust window switching mechanism.

2. Addressed inconsistencies in text processing that could occur due to timing issues.

#### Other Changes

1. Updated the documentation to reflect all new features and changes.

2. Improved code comments for better readability and maintainability.

3. Optimized the overall script structure for better performance and reliability.
