# BCR2000
## What is the goal ?
The goal is to use a grandma2/dot2 with a Behringer BCR2000 (or BCF2000) or just any midi controller using feedback.

## How to install ?
Just open the file with Chataigne after installing the GmaMsc module.

### Notes about the execs
If you use the bcr preset 22,

On the Chataigne side, the execs are organized like this :
  * first group of encoders : exec 1 to 8
  * second group of encoders : exec 11 to 18
  * third group of encoders : exec 21 to 28
  * fourth group of encoders : exec 31 to 38

And on all the presets, the 3 lines of knobs are always assigned to :
  * first line : exec 61 to 68
  * second line : exec 71 to 78
  * third line : exec 81 to 88

I am not using lines 41 to 48 and 51 to 58 because it looks like having a bug in msc that the desk is interpreting 46 (2E) as a dot and all the 5x exec like ascii time.

## files

#### macros-order.ods
    This is a personnal sheet to organize myself with assignations.

#### gmamsc-bcr2000.noisette
    This is a Chataigne file to load and make the thing work :)

### BCR side folder
    You need to use the software called [BC Manager](https://mountainutilities.eu/bcmanager).
    This software is better than the BcEdit furnished by Behnringer.

    I will not explain how to use bcmanager.

    Inside the "bcr-side" folder, there are some bcmanager files :

#### bcmanager-all-presets.bcr
    All the bcr presets from 1 to 22. I have loaded the factory ones and added 3 ones at 20 thru 22.

#### bcmanager-preset-20-encoders-full.bcr
    Only the preset 20 :
      * the encoders are configured to be able to use grandma encoders.
      * the "Encoder groups" buttons are not using midi and they just change encoder group

#### bcmanager-preset-21-encoders-1line.bcr
    Only the preset 21 :
      * the encoders are configured to be able to use grandma encoders.
      * But the "encoder groups" buttons are sending midi notes so there is only one encoder group and Chataigne will manage the 4 layers (or more if you need)

#### bcmanager-preset-22-execs.bcr
  Only the preset 22 :
    * only notes for buttons and controllers for execs)

### ma-side folder
  Here are 3 files :

#### dot2-gmamsc-start-show.gz
    The dot2 desk is not offering import/export capabilities and the commands are limited so i have made a simple start show to begin.

#### gmamsc-macros.xml
    Here are some macros to use.
      Tip: organize your view to have 8 macros horizontally and then you can organize them by columns to reflect the bcr.
    The best is to import them beginning at 305.

#### gmamsc-midiremotes.xml
    This is a midi remotes assignation example.
    As you can see, there are no faders and notes are just firing macros so you can keep the midi config and just move macro to change your setup.


## Notes about the BCR/BCF and windows 10.
    Usually, this is difficult to get the bcr/bcf running under windows.
    Here are the notes i have taken :
      * the usb liaison is better using a usb1 or usb2 port.
      * no need to install the Behringer driver because there is already a working one from Microsoft (the issues are the same using the Behringer or the Microsoft driver).
      * i am using MidiOx to test if the controller is responding (sometimes, it is recognized but no midi input is seen).
      * be patient, start the computer, start the bcr, restart the computer or plug/unplug usb...
      * under the devices manager, sometimes there are some hidden  drivers so delete them and plug again (in the device manager, menu "view" then "show hidden devices")
      * when the controller is recognized and send midi, it is stable and can work without issue.
      * i have also disabled the ability for the usb root hub to turn off the device to save power.
