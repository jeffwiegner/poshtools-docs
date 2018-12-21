---
description: >-
  Provides the steps necessary for working with the standalone WinForm designer
  in VS Code.
---

# Windows Forms Designer

## Opening the Designer

To open the designer, issue the `PowerShell: Show Windows Forms Designer` command in VS Code. You will want to have an active PS1 file selected as this will be the main file that the editor will use. 

## Working with the Designer

The designer is very much like the standard Visual Studio designer. The design surface on the left allows you to modify your form. You can resize and delete controls from the bottom.

On the right right it provides a toolbox with controls that can be selected and placed on the form. The add a new control, click the control you'd like to place and then click the design surface of where you would like to place the control. 

Below the toolbox is the properties dialog. You can select a control and modify its properties within this control. 

On the bottom of the designer is a status bar. It displays the file that is being modified by the designer. An asterisk will be shown when the form is modified. 

![](../../.gitbook/assets/image%20%285%29.png)

## Event Handlers

To implement an event handler, double click on the control you'd like to add the event handler to. It will automatically generate the event handler code in Visual Studio Code. The line where the event handler was generated will be highlighted. 

## Running your form

The beta version of this form designer does not generate the code necessary to launch the form. To do so, you will want to add the following code to your `form.ps1` file. This code loads the WinForms assemblies, launches the designer file that has been generated by the designer and then shows the dialog. 

```text
[System.Reflection.Assembly]::LoadWithPartialName("System.Windows.Forms")
. "$PSScriptRoot\form.designer.ps1"
$Form1.ShowDialog()
```


