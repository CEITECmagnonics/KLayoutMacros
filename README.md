# KLayoutMacros
Useful macros for KLayout.

These macros are used in the KLayout software, see its main page [here](https://www.klayout.de/).

User-defined macros (with the `.lym` extension) should be placed in the `macros` (ruby code) or `pymacros` (python code) folders in the KLayout installation folder. Actually, there are two poossible locations (both are usable):
- `C:\Users\<Username>\AppData\Roaming\KLayout` for global macros,
- `C:\Users\<Username>\KLayout` for local macros.

To use these scripts, copy the desired `.lym` files in one of those folders. Then run KLayout and open the _Macro Development_ window by clicking _Macro Development_ in the _Macros_ tab or pressing F5. Your copied fiels should be visible in one of the folders in the panel on the left. If not, try creating a new macro by clicking on _Create_ (+) and selecting _General KLayout Macro (.lym)_. Then copy the text from the file here to this new file, rename it and save it.

If you want to use the macro, you need to run the script first. After it finishes, you can go back to the KLayout's main window. When you would like to create an instance using that macro you just installed, select the macro in the _Libraries_ panel from the correct library and drag it onto the design.

There is a possibility to automatically run any macro at startup of KLayout. This can be selected in the _Macro Development_ window with opened desired macro file by clicking on _Edit properties of macro_ and checking _Run at startup_. Don't forget to save the file afterwards.
