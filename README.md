# Oled-3.12

xxxx  WORK in PROGRESS  xxxx

This is a fork from https://github.com/audiophonics/Evo_Sabre

The purpose is to use an OLED 3.12 inch with SSD1322 in an moOde Audio environment. 

This repository holds sources and methods developped originaly by Audiophonics for installing an OLED display 3.12 similar found in a EVO Sabre as second display.
Changes are required as GPIO connection of the display are different (RS and DC pins).

## Currently supported : 

### Display

The following display was tested with moOde 8.1.1 32bit:
https://www.aliexpress.com/item/32953790969.html?spm=a2g0o.cart.0.0.659b38dalhfGr0&mp=1

### Connection



### moOde audio
* Installation of OLED 3.12 Display
* Installation of IR remote - not done
* Installation of aptswi (web interface with some system options, see below) 

## APTSWI : Audiophonics ToolSet in a Web Interface
Some options can be configured by the user (such as OLED brightness, sleep-delay or boot logo) in a tiny web interface powered by nodeJS. 
You can get there by using your web-browser to open the **port 4150** : 
* On moOde Audio with http://moode:4150. 
* It works with your device IP as well : http://192.168.xx.xx:4150.

## Important notes from original Audiophonics: 
* **It should be generally safe to use this script on a non-fresh installation** of either Volumio or moOde if something broke after an update or if you messed with the configuration. However keep in mind that I designed this script for the purpose of building and debugging our custom releases and I could not test every possible scenario where the script would run on an already customized / configured device. Remember that you use this installation script at your own risks and that some extreme cases could lead you to reflash your SD card. So be sure to backup everything important (local music files on the SD card or the loggins for your volumio account) before doing anything. 

* **Most of what can be configured from the regular distro web interface is left untouched by this script**. If you use this installation method on a fresh install, you still have to configure Volumio / moOde in their WebUi (allowing MPD to control volume and such). Some distros may require the audio output to be already configured with the ES9038 driver to work. I suggest you do this in your regular distribution interface **before** running any customization script.

* **Your device must have network access to download dependencies.** This set of files is not designed for offline installation.

## Usage : 

* Update package repo list
```bash
sudo apt-get update
```

* Download source files (this repository).
```bash
git clone https://github.com/livs2021/Oled-3.12
```
* Enter directory.
```bash
cd Oled-3.12
```
* Each supported distribution has its own directory, enter the one corresponding to the distribution installed on your device. 
```bash
# for moOde audio
cd moode
```
* Run the installation script **as root** to install all available features
```bash
sudo bash install.sh
```

*most scripts deal with hardware configuration and will require you to reboot after completion. A successful script installation will explicitely notify you from terminal if a reboot is needed.*

## Install duration :
Some scripts and core functionnalities automatically download and compile frameworks from source. This is due to the wide range of Linux flavors that are found across the audio distributions for raspberry pi and the different rate at which updates happen. Since the defaults packages and libraries natively available on those systems can vary a lot, do not expect installation time to be consistent from one distribution to another. Installing OLED#2 can take about 5 minutes on moOde audio and up to 30 minutes on Volumio. 

