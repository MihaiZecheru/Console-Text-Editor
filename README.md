# Console Text Editor
C# class that implements a lightweight text editor--that accepts markup and is fitted with shortcuts--directly in the console window.

# Info
This class handles all the logic for writing text in the console.                                                                                                                                                                                                                    
The editor can be used for a variety of different things, comes                                                                                                                                                                                                                    
with markup support, and built-in shortcuts.                                                                                                                                                                                                                    

This editor's markup is made with `Spectre.Console`, making it a                                                                                                                                                                                                                    
project dependency.                                                                                                                                                                                                                    

To use this editor in a project, copy this file into your project                                                                                                                                                                                                                    
and give the project a namespace by uncommenting `line #6`.                                                                                                                                                                                                                    

Please note that there are `three` classes in this file that need to be                                                                                                                                                                                                                    
copied over for the editor to function. The `CtrlZ` class stores the                                                                                                                                                                                                                    
previous states of the note that is being written, allowing the                                                                                                                                                                                                                    
implementation of the `Ctrl+Z` and `Ctrl+Y` shortcuts (undo & redo).                                                                                                                                                                                                                    
The `TextEditorColors` class stores color hexes that are used when                                                                                                                                                                                                                    
writing markup text in the editor.                                                                                                                                                                                                                    

Open the editor by instantiating a `new TextEditor()` object,                                                                                                                                                                                                                    
then calling `textEditor.MainLoop()` on that object to open.                                                                                                                                                                                                                    

Open the editor to edit existing text by passing the text-to-edit                                                                                                                                                                                                                    
in when instantiating the TextEditor, ex:                                                                                                                                                                                                                    
`new TextEditor("hello world\nthis is the 2nd line").MainLoop()`                                                                                                                                                                                                                    

The `.MainLoop()` function looks like this:                                                                                                                                                                                                                    
```public bool MainLoop(ref string note_body, ref bool _isJson)```                                                                                                                                                                                                                    

When the user is done writing his note, he will press `Ctrl+S` and                                                                                                                                                                                                                    
the `.MainLoop()` function will return a success value indicating                                                                                                                                                                                                                    
whether the user finished writing his note and pressed `Ctrl+S`,                                                                                                                                                                                                                    
or whether he used `Ctrl+Q` to quit out of the editor, deleting his note.                                                                                                                                                                                                                    

The `note_body` and `_isJson` variables are passed by reference and                                                                                                                                                                                                                    
will contain what was written. `note_body` will hold the text itself,                                                                                                                                                                                                                    
and `_isJson` will hold a value indicating whether the note written                                                                                                                                                                                                                    
is only JSON text.                                                                                                                                                                                                                    

Made by Mihai Zecheru (2023)
