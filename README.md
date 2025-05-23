# rpi-spotify-matrix-display

A Spotify display for 64x64 RGB LED matrices from https://github.com/kylejohnsonkj/rpi-spotify-matrix-display

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

> [!IMPORTANT]
> Please see the [pi setup wiki page](https://github.com/kylejohnsonkj/rpi-spotify-matrix-display/wiki/raspberry-pi-full-setup-guide) for a full installation guide!

https://github.com/user-attachments/assets/9bf163f9-8e0f-47cc-b2d2-a62b3a975471

<sup>The above video is from [my reddit post here.](https://www.reddit.com/r/raspberry_pi/comments/ziz4hk/my_64x64_rgb_led_matrix_album_art_display_pi_3b/)</sup>

## Configuration
Configuration is handled in the config.ini. I have included my own as a sample.

For Matrix configuration, see https://github.com/hzeller/rpi-rgb-led-matrix#changing-parameters-via-command-line-flags. More extensive customization can be done in `impl/controller_v3.py` directly.

For Spotify configuration, set the `client_id` and `client_secret` to your own. You may leave `redirect_uri` alone. I have also included a `device_whitelist` which is disabled by default.

## Acknowledgements
Thanks to allenslab for providing the original codebase for this project, [matrix-dashboard](https://github.com/allenslab/matrix-dashboard). You can find his original reddit post [here](https://www.reddit.com/r/3Dprinting/comments/ujyy4g/i_designed_and_3d_printed_a_led_matrix_dashboard/). This project is an adaption of his Spotify app for 64x64 matrices, while also packing some other improvements.

Thanks to ty-porter for [his fork](https://github.com/ty-porter/matrix-dashboard) of matrix-dashboard from which my development branched from. The emulation support his [RGBMatrixEmulator project](https://github.com/ty-porter/RGBMatrixEmulator) added made it a breeze to develop efficiently.

And finally, thanks to hzeller for his work on [rpi-rgb-led-matrix](https://github.com/hzeller/rpi-rgb-led-matrix).
