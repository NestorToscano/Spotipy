# rpi-spotify-matrix-display
![My Logo](./IMG_7990.png)


A Spotify display for 64x64 RGB LED matrices from https://github.com/kylejohnsonkj/rpi-spotify-matrix-display that I wanted to make as a present for someone special to me.

## Hardware
- Adafruit 64x64 rgb led matrix (2.5mm pitch)

- Adafruit matrix bonnet (modded for pwm and address E line to support a 64x64 matrix)

- raspberry pi zero W headers

- 32GB microSD card (loaded with pi OS lite)

- 5v 10a switching psu

- 3d printed case ( https://www.thingiverse.com/thing:6687509#google_vignette )
  - Screws

## Spotify Pre-Setup
1. Go to https://developer.spotify.com/dashboard
2. Create an account and/or login
3. Select "Create app" (name/description does not matter)
4. Add http://127.0.0.1:8080/callback under Redirect URIs
5. Save, then tap "Settings" in the upper right
6. Copy the generated Client ID and Secret ID for later

## Pi Setup
Followed this guide for a the software side (https://github.com/kylejohnsonkj/rpi-spotify-matrix-display/wiki/raspberry-pi-full-setup-guide). Some tweaks were necessary and packages such as libopenblas-dev and python dev tools. Also used 'sudo nmtui' to alter the network settings to allow multiple wifi connections at different spots. Also used nano instead of vim (personal preference)

## Configuration
Configuration is handled in the config.ini. I have included my own as a sample.

For Matrix configuration, see https://github.com/hzeller/rpi-rgb-led-matrix#changing-parameters-via-command-line-flags. More extensive customization can be done in `impl/controller_v3.py` directly. I added my APIs id's to the config.ini file, and i made sure to change the matrix config for the pi zero. It was a slightly slower board, so no gpio slowdown was needed, and i used the adafruit bonnet so that needed to be changed as well.

## Acknowledgements
Thanks to kyle johnson (https://github.com/kylejohnsonkj/rpi-spotify-matrix-display) for providing the software and overall guide to completing this project for myself. Other versions of this project had various outdated package and os issues that arose while doing this project, but this was the most recent (somewhat) working implementation i could find (even if it took a few days to debug all the issues ;-;).
