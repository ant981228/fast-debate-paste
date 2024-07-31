# Window Switcher and Text Processor (v1.2)

## Overview

This utility provides a convenient way to copy text from one window, process it according to specific patterns, and paste it into a pre-selected target window. It's particularly useful for repetitive tasks that involve transferring and formatting text between different applications.

## Features

1. Persistent target window selection
2. Text processing for specific patterns, including abbreviated words
3. Hotkeys for quick operation
4. Error handling for unavailable windows and clipboard operations
5. Improved timing and reliability for text processing operations
6. Retry mechanism for more consistent regex matching

## Installation

1. Download the executable file.
2. Place the file in a convenient location on your computer.
3. Run the executable to start the program.

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
5. The program will copy the selected text, process it if it matches a specific pattern, switch to the target window, paste the processed text, and switch back to the source window.

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
- The program now includes a retry mechanism that attempts to process the text multiple times if necessary, improving the consistency of the regex matching.

## Error Handling

- If you try to use `Ctrl+Shift+C` without selecting a target window, you'll be prompted to select one.
- If the target window is no longer available when you try to paste, you'll be notified and asked to select a new target window.
- If the program fails to copy text to the clipboard, you'll receive an error message and be asked to try again.

## Troubleshooting

- If hotkeys don't work, check for conflicts with other applications.
- If text isn't being processed as expected, the program will make multiple attempts to process it. In rare cases where processing still fails, the original text will be pasted unchanged.
- If you consistently experience issues with text processing, try selecting the text again and re-copying, as this can sometimes resolve clipboard-related issues.
- For any other issues, try restarting the program or rebooting your computer.
- Ensure the program is running with appropriate permissions.

## Support

For support, please contact the program developer or refer to any provided support channels.

Remember to always back up your work and use this utility responsibly.
