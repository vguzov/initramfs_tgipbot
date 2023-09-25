# Telegram IP address notification bot for initramfs
This is a simple script that sends your IP address through your Telegram bot when your system boots up. 
It is useful when you have a headless server with encrypted partition, and you want to know its IP address without having to connect a monitor to it.
**Tested on Ubuntu 22.04**

## How to install 
1. Install dropbear-initramfs. 
   - Just `sudo apt install dropbear-initramfs` is usually enough. For more detailed configuration, I found this guide useful: https://www.cyberciti.biz/security/how-to-unlock-luks-using-dropbear-ssh-keys-remotely-in-linux/
2. Drop `script/telegramip` file to `/usr/share/initramfs-tools/scripts/init-premount/`
3. Fill in your Telegram bot token and chat id in the `telegramip` file. You can get them from [BotFather](https://t.me/botfather) and [userinfobot](https://t.me/userinfobot)
4. Set up curl by copying `hook/curl` to `:/usr/share/initramfs-tools/hooks/curl`
5. Run `sudo update-initramfs -u`