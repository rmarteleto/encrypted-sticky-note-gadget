# Introduction #

This page shows how the encrypted sticky note gadget works and attempts to answer questions that user may have.

# How to use Encrypted Sticky Note gadget #

## Initial state ##
The initial state of this Google gadget presents no _text_ and no _key_. Users can type any text they want.

## Saving text ##

Text is saved on three different events and requires no direct user intervention:
  * text textbox loses focus
  * text textbox mouse out
  * key textbox loses focus

The key input field is of password type, meaning that it is not readable while being typed. When users enter the key for the first time or the key is changed, a confirmation dialog is displayed so users can confirm that key that was entered. The key string is readable in the confirmation dialog. This confirmation dialog is not shown when user is just trying to decrypt an existing encrypted text. When _Activate key_ checkbox is checked, _key_ textbox becomes readonly, its color becomes red. When _Activate key_ checkbox is not checked, _key_ textbox is editable, and its color becomes green.

During the text saving process, if _Activate key_ checkbox is checked, text will be encrypted and then the encrypted result is saved. if _Activate key_ checkbox is not checked, encryption will not be used and plain text is saved.

### Text length limitation ###

Google gadgets have limitations on the amount of data it can handle. Encrypted Sticky Note gadget will warn users when text to be saved exceeds 2000 characters. A warning/error message will be displayed on the top part of the gadget, above the key/password editbox, in red letters. **No text is saved** while warning is displayed. Users must delete parts of the text in order to allow gadget to save again. Users may use more than one instance of Encrypted Sticky Note in iGoogle if wanted.

## Loading text ##

When gadget is loaded, it retrieves data to populated its _text_ textbox and recognizes if text is encrypted or not. If text is not encrypted, it is automatically diplayed in _text_ textbox. If text is encrypted, a _Text is encrypted_ message is shown in _text_ textbox until user 1)types the (correct) key in _key_ textbox and 2) activates the key by checking the _activate key_ checkbox.

Upon checkbox click, text will be automatically decrypted and displayed on _text_ textbox and key locked if the typed key is correct. If key is incorrect, a _incorrect key_ message will be displayed and user will be able to type the correct key.

## Adding/Changing key ##

If this is the first time adding a key, just type it in _key_ textbox and then activate it by checking _activate key_ checkbox.

If you are already encrypting your text with a key and wishes to modify it, you have to first decrypt your text. Plain text must be shown on _text_ textbox (it might be empty). If _activate key_ checkbox is checked, uncheck it to be able to edit the key. After you are done changing your key, make sure you check _activate key_ checkbox back, otherwise text will be saved as plain text.

Remember that a dialog will be displayed with your new key for confirmation. The key is readable in the dialog, so make sure nobody is watching what you have entered. Click OK to confirm your new key, or CANCEL to change the key again.

## Reseting key ##

If you forgot what your key is, this is not the end of the world. The good news is that you will be able to reset your key and continue to use this gadget. **The bad news is that you will lose text that has been encrypted and saved before**. There is no way of discovering which key you used other than using brute force (as of April 2009), which may take over 1000 years to figure it out. The time to crack AES-256 actually depends on your key/password.

To reset your key, enter "**Reset my key, please**" as the key and activate key (check _activate key_ checkbox). **Remember that you will lose your text.**

# Gadget Setting #

This gadget allows users to modify a couple of settings. To do so, expand the gadget context menu and click on _Edit settings_:
  * Gadget title: simply modifies the gadget title. The default value is _Encrypted Sticky Note_;
  * Gadget labels: there are 3 fields in this gadget. One textbox for the key, one textbox for general text, and one checkbox for key activation. When _show labels_ is **No**, no label is shown for the 3 fields. When _show label_ is **Partial**, only labels for key and text area are shown. When _show label_ is **Full**, all labels are shown (it is the default value).