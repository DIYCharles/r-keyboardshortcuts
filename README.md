#Welcome to the /r/Keyboardshortcuts Wiki!

This wiki is designed to help the community by providing info in one easy-to-use place. 

This sub is under new moderation and is currently a work in progress. Any support is welcome

----

Table of contents
=================

   * [What is a Keyboard Shortcut](#What-is-a-Keyboard-Shortcut)
   * [Different Types of Shortcuts](#Different-Types-of-Shortcuts)
   * [Operating System Shortcuts](#Operating-System-Shortcuts)
   * [Program Specific Shortcuts](#Program-Specific-Shortcuts)
   * [Keyboard Firmware Shortcuts](#Keyboard-Firmware-Shortcuts)
   * [Third Party Shortcut Programs](#Third-Party-Shortcut-Programs)

What is a Keyboard Shortcut 
============

In computing, a keyboard shortcut is a sequence or combination of keystrokes on a computer keyboard which invokes commands in software.

Most keyboard shortcuts require the user to press a single key or a sequence of keys one after the other. Other keyboard shortcuts require pressing and holding several keys simultaneously.

Different Types of Shortcuts 
============
There are many ways to use shortcuts and most can be customized. Here is a general categorization of the ways shortcuts are used. 

* **Operating System Shortcuts** - Can be executed globally and usually do not need any pre-configuration to work. 
* **Program Specific Shortcuts** - Applications like the Adobe CS have a plethora of shortcuts that are both standard and configurable.
* **Keyboard Firmware Shortcuts** - With a programmable keyboard you can create keymaps that contain shortcuts hard coded into the firmware. A single key can be used to represent a combination of keys, an input string such as a password, or even several different keys and strings separated but defined amounts of time.
* **Third Party Shortcut Programs** - These are shortcuts that use a third party software that has to be configured on the OS in order to execute a complex command. 


Operating System Shortcuts 
============
Here are some links to shortcuts based on operating systems.

* [Windows](https://support.microsoft.com/en-us/help/12445/windows-keyboard-shortcuts)
* [Mac](https://support.apple.com/en-us/HT201236)
* [Ubuntu](https://help.ubuntu.com/stable/ubuntu-help/shell-keyboard-shortcuts.html.en)

[Here is a guide on how to make a keyboard shortcut to run any program or batch script on windows.](https://github.com/DIYCharles/r-keyboardshortcuts/blob/master/Creating%20bat%20Shortcuts/README.md) Batch scripts can be used for almost anything. The examples extend the display to a second monitor and show only on the main monitor with the keys Ctrl+alt+down and Ctrl+alt+up respectively. This method can be used with base windows and needs no third party software. 

![alt text](%%img7%%)
  
Program Specific Shortcuts 
============
Here are some links to shortcuts based on program.

* [Word](https://support.microsoft.com/en-us/office/keyboard-shortcuts-in-word-95ef89dd-7142-4b50-afb2-f762f663ceb2)
* [Excel](https://support.microsoft.com/en-us/office/keyboard-shortcuts-in-excel-1798d9d5-842a-42b8-9c99-9b7213f0040f)
* [Teams](https://support.microsoft.com/en-us/office/keyboard-shortcuts-for-microsoft-teams-2e8e2a70-e8d8-4a19-949b-4c36dd5292d2)

Keyboard Firmware Shortcuts 
============
These are some of the most configurable and easy to remember shortcuts because instead of needing to memorize the combinations of several keys you can program the entire shortcut to a single key. Using qmk you can program different layers so a single key can pull the entire keyboard up a level to access more shortcuts on the same keys. This makes all the space on your keyboard usable. Some examples of the usage are below

* **Key Combos** - Simple keys that are pressed together
* **String input** - A single key press can input and entire string like a password or the entire bee movie script
*  **Complex Macros** - A combination of key clicks and/or strings separated by a defined amount of time. For example you can run something like Windows key+R, wait 10ms, string input "cmd", enter, wait 10ms, string input "ipconfig /all", enter. With this you can see your network statistics with a single click.
*  **Paths to execute a script** - This allows you to make shortcuts that are only limited by your creativity. For example on my desktop I have to .bat files that extend my display to another monitor and show only on 1 monitor. These are exicuted by a single key that points to that script and executes it. 

[Here is an example of how the shortcuts can be used.](https://github.com/DIYCharles/DIYKeyboards-/blob/master/README.md) This example is a 4 key macropad with a rotary encoder. These are the shortcut keys mapped

* LCTL(KC_Z) **Undo**
* LCTL(KC_C) **Copy**
* LCTL(KC_V) **Paste**
* LCTL(LSFT(KC_M)) **Mute mic in MS Teams**
* KC_MUTE **Rotary encoder push button mutes speakers**

```
const uint16_t PROGMEM keymaps[][MATRIX_ROWS][MATRIX_COLS] = {KEYMAP(LCTL(KC_Z), LCTL(KC_C), LCTL(KC_V), LCTL(LSFT(KC_M)), KC_MUTE),
} 
```

The rotary encoder is mapped in the keymap.c file with

* KC_AUDIO_VOL_UP and KC_AUDIO_VOL_DOWN **Turns the volume up and down**
  
```
void encoder_update_user(int8_t index, bool clockwise) {
    if (clockwise) {
      tap_code(KC_AUDIO_VOL_UP);
    } else {
      tap_code(KC_AUDIO_VOL_DOWN);
    }
}
```

Third Party Shortcut Programs 
============
[AutoHotKey](https://www.autohotkey.com/)


" *AutoHotkey is a free, open-source scripting language for Windows that allows users to easily create small to complex scripts for all kinds of tasks such as: form fillers, auto-clicking, macros, etc. Define hotkeys for the mouse and keyboard, remap keys or buttons and autocorrect-like replacements. Creating simple hotkeys has never been easier; you can do it in just a few lines or less!* "

----
#### This wiki is a work in process. If you would like to contribute contact u/DIYEngineeringTX and I'll show you how to help.