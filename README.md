# KLayoutMacros
Useful macros for KLayout.

These macros are used in the KLayout software, see its main page [here](https://www.klayout.de/).

User-defined macros (with the `.lym` extension) should be placed in the `macros` (ruby code) or `pymacros` (python code) folders in the KLayout installation folder. For Windows, there are two possible locations (both are usable):
- `C:\Users\<Username>\AppData\Roaming\KLayout` for global macros,
- `C:\Users\<Username>\KLayout` for local macros.

To use these scripts, copy the desired `.lym` files in one of those folders. Then run KLayout and open the _Macro Development_ window by clicking _Macro Development_ in the _Macros_ tab or pressing F5. Your copied files should be visible in one of the folders in the panel on the left. If not, try creating a new macro by clicking on _Create_ (+) and selecting _General KLayout Macro (.lym)_. Then copy the text from the file here to this new file, rename it and save it.

If you want to use the macro, you need to run the script first. After it finishes, you can go back to the KLayout's main window. When you would like to create an instance using that macro you just installed, select the macro in the _Libraries_ panel from the correct library and drag it onto the design.

There is a possibility to automatically run any macro at startup of KLayout. This can be selected in the _Macro Development_ window with opened desired macro file by clicking on _Edit properties of macro_ and checking _Run at startup_. Don't forget to save the file afterwards.


<hr>

## Tips for python development of KLayout macros

KLayout is written primarily in Ruby, therefore also the [API documentation](https://www.klayout.de/doc-qt5/index.html) (especially the [Class Index](https://www.klayout.de/doc-qt5/code/index.html) can be useful) is written only in Ruby. There may be differences between Ruby and Python implementations, which means, that there are mission information. Quite helpful can be using the `help()` command and temporarily print its contents mid-macro development.

There is also quite high chance, that the bugs I report here, are just de to an older version of KLayout. My current version of KLayout is 0.27.1 (appropriate documentation [here](https://www.klayout.de/0.27/doc/code/class_PCellDeclarationHelper.html)).

- Inserting shapes to a cell/layer has to be done directly (`self.cell.shapes(self.l_layer).insert(pya.Box(...))`, not `box_obj=pya.Box(...);self.cell.shapes(self.l_layer).insert(box_obj)`). I don't know why, but inseting objects of shapes is not working.
 