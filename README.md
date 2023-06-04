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
10. Disable "USB key inserted notification" (currently this is by hand, I'm not aware of a command to do it):
  - Open a file browser GUI window.
  - On the top bar, click "Edit"..
  - On the menu, click "Preferences".
  - In the left pane of the new window, click "Volume Management".
  - Ensure that everything is ticked EXCEPT "Show available options for removable media when they are inserted".
  - Close the preferences window and the file browser window.
  - # Could improve this by copying the contents of .config/pcmanfm out after a complete setup, then back in during prep.
11. Set speaker station to run on startup: echo "~/speaker_station/bin/python ~/speaker_station/speaker_station" >> ~/.bashrc
# From here
12. Give it a test run by rebooting, ensuring the speaker station runs on one monitor, and when you insert a USB key containing presentations (then hit r) you can present them as expected.
13. Remember to clear out any bash history, SSH keys or Wifi credentials you used during prep, and probably system logs.
14. You can now power off and copy the image somewhere for posterity.
