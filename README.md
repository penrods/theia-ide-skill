# <img src='theia.png' card_color='#40DBB0' width='50' style='vertical-align:bottom'/> Theia IDE
Create your own skills and learn to code

## About
Edit Python code directly on your Mycroft device using a web browser.

## Description
This installs [Theia IDE](https://www.theia-ide.org/index.html) on your Mycroft device. Theia makes it easy to create and edit Python skills for Mycroft. Theia IDE integrates with GitHub, and you can use Mycroft tools like `mycroft-msm` and `mycroft-msk` directly from the IDE's integrated shell. Theia is built on the excellent open source VS Code editor from Microsoft.

Explore the skills of others for ideas and learn to code your own Skills!  The built-in highlighting and dynamic code hints help take the tedium out of programming, letting you focus on what you want to make.

<img src='screenshot.png' card_color='#40DBB0' width=800 style='vertical-align:bottom'/>

## How to install
Install this skill from the Mycroft Marketplace or by running this command:
```
mycroft-msm install https://github.com/andlo/theia-ide-skill.git
```
During installation a precompiled package is downloaded and extracted.

When done, there should be a log saying "Starting THEIA IDE" and Mycroft should inform you it is ready for use.
You can then open a web-browser and go to http://picroft:3000 if your Mycroft device is Picroft, or http://mark_1:3000 for a Mark 1.  Alternately you can ask Mycroft "what is my IP" and use that information to build a URL such as:  https://192.168.1.33:3000.

The Skill Settings on https://home.mycroft.ai/ have one checkbox for setting autostart or not.  If not set to autostart, you must first tell Mycroft to turn on Theia by saying "Hey Mycroft, activate IDE".

__WARNING__: There is no password protection to access the IDE and the integrated terminal.  Think twice before setting autostart and exposing your device to the internet.

## Updating the THEIA package
To update the precompiled binaries from my [Theia for Mycroft repo](https://github.com/andlo/theia-for-mycroft), remove and reinstall this skill.

## Mark 1
On a Mark 1 the default firewall needs to be opened. SSH to your Mark 1 and run the follow command:
```
sudo ufw allow from any to any port 3000 proto tcp
```

## Git integration
The IDE doesn't have a way to directly set your username and password to GitHub. To get integration to work seamlessly,
you can configure  `git` to remember your username and password.

This is done via these three git commands.  SSH to your device or use the integrated terminal direcly in the IDE, then enter:
```
git config --global credential.helper store
git config --global user.name "your_username"
git config --global user.password "your_password"
```

__WARNING__: Your git account passwords are saved in plaintext format in the global .gitconfig file, e.g under "/home/pi/.gitconfig".  If security is a concern, you can use an SSH key for your account instead.

## Examples
* "Activate IDE"
* "Deactivate IDE"
* "Restart IDE"

## Credits
Andreas Lorensen (@andlo)

## Supported Devices
platform_mark1 platform_picroft

## Licensing
This skill is licensed by GNU GENERAL PUBLIC LICENSE Version 3 - https://github.com/andlo/theia-ide-skill/blob/master/LICENSE

The skill installs other software with different licenses.
* Theia-ide is licensed by Eclipse Public License version  2 - https://github.com/theia-ide/theia/blob/master/LICENSE
* Git is licensed by GNU GENERAL PUBLIC LICENSE Version 2 - https://github.com/git/git/blob/master/COPYING
* Node.js seems to have its own license - https://github.com/nodejs/node/blob/master/LICENSE

## Category
**Productivity**

## Tags
#theia
#IDE
#editor
#dev
#vscode
#python
