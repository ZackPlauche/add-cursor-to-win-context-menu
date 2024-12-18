# Add Cursor to Windows Context Menu Scripts
![image](https://github.com/user-attachments/assets/d9428754-03d9-45c9-a0b6-b1628f6dd2ea)

I found the "Add VSCode to Context Menu" option really useful when VSCode was my main editor so I wanted to make a script to add Cursor to the context menu as well.

I'm posting these here so they exist on the internet somewhere.

## Instructions
- ***IMPORTANT NOTE:*** I built this on a Windows 11 machine. I'm not sure if it will work on other versions of Windows. Let me know somewhere if it does!

- ***IMPORTANT NOTE 2:*** This will only work if you install cursor to `C:\Users\<username>\AppData\Local\Programs\cursor\Cursor.exe`

There are 2 files here:
1. add_cursor_to_context_menu.reg - Adds cursor to your context menu (of course)
2. remove_cursor_from_context_menu.reg - Removes cursor from your context menu

I think it's pretty straight forward but if not:

### To Install

1. Download the `add_cursor_to_context_menu.reg` file if you want to add it **OR** copy the code and paste it in your own file.
2. Run the file.
3. Click yes to all the prompts and it should be added to your context menu.

Here's the code for convenience (it's not a lot):
```reg
Windows Registry Editor Version 5.00

; Add "Open with Cursor" context menu for folders
[HKEY_CLASSES_ROOT\Directory\shell\OpenWithCursor]
@="Open with Cursor"
"Icon"="C:\\Users\\zackp\\AppData\\Local\\Programs\\cursor\\cursor.exe"

[HKEY_CLASSES_ROOT\Directory\shell\OpenWithCursor\command]
@="\"C:\\Users\\zackp\\AppData\\Local\\Programs\\cursor\\cursor.exe\" \"%V\""

; Add "Open with Cursor" context menu for the background of folders
[HKEY_CLASSES_ROOT\Directory\Background\shell\OpenWithCursor]
@="Open with Cursor"
"Icon"="C:\\Users\\zackp\\AppData\\Local\\Programs\\cursor\\cursor.exe"

[HKEY_CLASSES_ROOT\Directory\Background\shell\OpenWithCursor\command]
@="\"C:\\Users\\zackp\\AppData\\Local\\Programs\\cursor\\cursor.exe\" \"%V\"" 
```


### To Remove

1. Download the `remove_cursor_from_context_menu.reg` file if you want to add it **OR** copy the code and paste it in your own file.
2. Run the file.
3. Click yes to all the prompts and it should be removed from your context menu.

Here's the code for convenience:

```reg
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\Directory\shell\OpenWithCursor]
[-HKEY_CLASSES_ROOT\Directory\Background\shell\OpenWithCursor] 
```
