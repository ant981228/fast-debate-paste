## Initial Setup
When you run the program for the first time, it will prompt you to select a target window. This is the window where the copied text will be pasted.

## Hotkeys
The program uses two main hotkeys:

Ctrl+Shift+W: Opens a window selection dialog to change the target window.
Ctrl+Shift+C: Performs the copy-paste operation.

## Workflow

Run the executable.
Select your initial target window from the popup dialog.
Go to the source window and select the text you want to copy.
Press Ctrl+Shift+C.
The program will copy the selected text, process it if it matches a specific pattern, switch to the target window, paste the text, and switch back to the source window.

## Changing the Target Window
If you need to change the target window at any time:

Press Ctrl+Shift+W.
Select the new target window from the popup dialog.
Click OK.

## Figure and Table Omissions
The program includes a text processing feature:

If the copied text matches the pattern "WORD NUMBER" (e.g., "Figure 2.1" or "Table 3.2.1"), it will be transformed to "[WORD NUMBER OMITTED]" in all caps.
If the text doesn't match this pattern, it will be pasted as-is.

## Error Handling

If you try to use Ctrl+Shift+C without selecting a target window, you'll be prompted to select one.
If the target window is no longer available when you try to paste, you'll be notified and asked to select a new target window.

## Troubleshooting

If hotkeys don't work, check for conflicts with other applications.
For any other issues, try restarting the program or rebooting your computer.
Ensure the program is running with appropriate permissions.

