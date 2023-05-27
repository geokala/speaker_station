# Speaker station for PyconUK

This should (soon) be able to run on a Raspberry Pi and display arbitrary presentations in a helpful way.

## DIY instructions

1. (Recommended) Flash your SD card to ensure a clean starting image. This was tested with https://downloads.raspberrypi.org/raspios_arm64/images/raspios_arm64-2023-05-03/2023-05-03-raspios-bullseye-arm64.img.xz
2. (Recommended) Set up your newly installed image with a user called 'speaker'
3. Ensure all software is up to date: sudo apt-get update && sudo apt-get dist-upgrade -y
4. Install prerequisites: sudo apt-get install pdf-presenter-console gstreamer1.0-gtk3 libreoffice-impress -y
5. Clone the speaker station code: git clone https://github.com/geokala/speaker_station ~/speaker_station
6. Prepare a venv: python3 -mvenv ~/speaker_station
7. Install prerequisites: ~/speaker_station/bin/pip install ~/speaker_station/requirements.txt
8. Insert a USB key to ensure appropriately permissioned /media subdir exists.
9. Set desktop background pcmanfm --set-wallpaper ~/speaker_station/wallpaper.png
# From here
10. Disable "USB key inserted notification" (how?)
11. Set ~/speaker_station/bin/python ~/speaker_station/speaker_station to run on startup (how?)
12. Give it a test run by rebooting, ensuring the speaker station runs on one monitor, and when you insert a USB key containing presentations (then hit r) you can present them as expected.
13. Remember to clear out any bash history, SSH keys or Wifi credentials you used during prep.
14. You can now power off and copy the image somewhere for posterity.
