# Fast Debate Paste (v1.6)

## Overview
Fast Debate Paste is a utility designed to streamline the process of copying text from various sources and pasting it into a card processing document for debate preparation. It offers advanced text processing features, customizable hotkeys, and seamless integration with Zotero.

## New Features in v1.5
- **Copy-Paste Without Line Breaks**: New function to remove line breaks while copying text, ideal for pasting from PDFs with line breaks within paragraphs.
- **Copy-Paste Without Line Breaks and Return**: A variant that doesn't add a line break before the copied content, useful for paragraphs spanning page breaks.
- **Clone Last Cite**: Replaced the undo function with a "Clone Last Cite" feature, which goes to the target window and presses Alt + F8 (Verbatim shortcut for cloning the last cite).
- **Enhanced Text Processing**: Improved handling of hyphenated numbers and multiple periods in omitted figures/tables/equations.

## Key Features
- Persistent target window selection
- Advanced text processing for specific patterns, including figure/table/equation omissions
- Customizable hotkeys via INI file
- Toggle emphasis style for omissions
- Built-in help dialogue
- Zotero integration for quick debate citations

## Installation
1. Download the executable file.
2. Place the file in a convenient location on your computer.
3. Run the executable to start the program.
4. On first run, the program will create a `Hotkeys.ini` file in the same directory.

## Zotero and Zutilo Setup (Optional)
For Zotero integration:
1. Install the Zutilo extension for Zotero.
2. Configure Zutilo's "QuickCopy items" to use the Ctrl + 0 hotkey.
3. Set up Zotero's QuickCopy output format in preferences.

## Usage

### Default Hotkeys
- `Ctrl+Shift+W`: Open window selection dialog
- `Ctrl+Shift+C`: Perform copy-process-paste operation
- `Ctrl+Shift+Z`: Clone last cite
- `Ctrl+Shift+H`: Display help dialogue
- `Ctrl+Shift+V`: Copy-paste without line breaks
- `Ctrl+Shift+B`: Copy-paste without line breaks and return

### Workflow
1. Run the executable and select your target window.
2. In the source window, select text to copy.
3. Use the appropriate hotkey for your desired action (standard copy-paste, no line breaks, etc.).
4. The program will process the text and paste it into the target window.

### Zotero Workflow
1. Select Zotero items to copy.
2. Press `Ctrl+Shift+C` to perform Zotero Quick Copy and paste to your target window.

## Text Processing
- Reformats omitted figures, tables, and equations (e.g., "Figure 2.1" becomes "[FIGURE 2.1 OMITTED]").
- Handles standalone numbers as equation omissions.
- Processes hyphenated numbers and multiple periods in omitted items.

## Customization
Edit the `Hotkeys.ini` file to customize hotkeys and settings:
- Modify values in the `[Hotkeys]` section to change hotkey assignments.
- In the `[Settings]` section, toggle `ApplyF10ToProcessedText` for to choose whether you want emphasis styling applied to processed text.

## Troubleshooting
- Verify hotkey conflicts with other applications.
- Check `Hotkeys.ini` for correct configuration.
- Ensure proper Zutilo and Zotero setup for citation integration.
- For persistent issues, try restarting the program or rebooting your computer.

## Support
For support, please contact the program developer or refer to provided support channels.

Remember to always back up your work and use this utility responsibly.
