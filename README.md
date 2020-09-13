# Twirling Rhythm

"Twirling Rhythm" is a sample rhythm game that runs on APL 1.3.

# ScreenShot

! [screenshot](https://raw.githubusercontent.com/mokomoko-don/alexa-apl-rythem-game-sample/master/images/rhythm_640.jpg)

# Features

This code runs on alexa, which is implemented in the Amazon Echo Show series and others.

New in APL 1.3, we took advantage of localTime to create a simple rhythm game.

# Requirement

 * Actual device running Alexa
 * AlexaDeveloperConsole account
 * Knowledge of simple custom skill creation

# Installation

## Sound Source Preparation (optional)
You don't need music to run this source, but if you want to check the agreement between the screen and the sound, you need to prepare the music according to the following procedure due to the license.

By the way, I made the data of the marker based on the following music.
https://dova-s.jp/bgm/play12934.html

Convert mp3 to mp4 using ffmpeg or web tool. The video part will not be displayed, but you must combine it with some dummy video or image for Alexa to load correctly.

Example: music.mp3 and dummy.png to music.mp4

````
ffmpeg -loop 1 -r 30000/1001 -i dummy.png -i music.mp3 -c:a copy -c:v libx264 -pix_fmt yuv420p -shortest music.mp4
````

## How to activate it as a skill during development

 * Create a HelloWorld skill in AlexaDeveloperConsole (AlexaHostedSkill).
 * Enter any skill name.
 * Press "Interfaces".
 * Enable "Alexa Presentation Language".
 * Press "Save Interface".
 * Go to "Interaction Model" -> "JSON Editor".
 * Copy and paste "/interactionModels/custom/ja-JP.json".
 * "Save Model" and "Build Model".
 * Go to code editor.
 * Copy and paste all files under "/lambda".
 * Replace line 445 of "/lambda/apl/rolling.json" with the actual URL.
 * Save and deploy.
 * Go to the "Test" screen.
 * Change "Off" to "Development" in the pull-down menu.

## How to run on the APL editor

 * Create a HelloWorld skill in AlexaDeveloperConsole (AlexaHostedSkill).
 * Enter any skill name.
 * On the "Build" screen, press "Multimodal Responses".
 * Press "Visual" and "Create Visual Response".
 * Press "Upload Code".
 * Load "aplEditor/apl_template_export.json".
 * Press "Save Template" at the top right of the screen

# Usage

## How to activate it as a skill during development

Launch from the actual device with "Alexa, open *****".
(In a PC simulator, the screen and sound are out of sync.)

## How to run on the APL editor

On the APL editor screen, press the actual output button at the bottom of the output simulation.
(In a PC simulator, the screen and sound are out of sync.)

## How to play

If you press the PUSH button when the marker (capsule) is at the left end of the circle, the marker will disappear and you will get a score.

# Note
As of September 2020, the system has been confirmed to work. Please note that we do not guarantee the operation if it stops working due to specification changes in the future.

# Author

* kyukkyu
* Twitter : https://twitter.com/Synoyan

# License

"Twirling rhythm" is under [MIT license] (https://en.wikipedia.org/wiki/MIT_License).
