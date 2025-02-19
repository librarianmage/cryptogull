# Welcome!
This project is spearheaded by the Trash Monks wiki editing team for the Caves of Qud community. We coordinate in the [official Caves of Qud Discord server](https://discordapp.com/invite/cavesofqud) (invite link).

Contributions from the community in the form of issues or pull requests are welcomed. The Trash Monks team is also available to join on the Discord server by asking any of the Mayors there.

This project uses the Code of Conduct available from that Discord server, in the `#code-of-conduct` channel.

# Environment setup
To develop on this project, you first need to have Python 3.8 installed on your system. For Windows users, install the latest 3.8 installer from [here](https://www.python.org/downloads/windows/). Choose the option to add Python to your PATH environment variable. For Debian-derived Linux distributions, `sudo apt install python3.8 python3-pip`.
 
The second requirement is Git. For Windows users, install [Git for Windows](https://git-scm.com/download/win) and use the default options. For Debian-derived Linux distributions, `sudo apt install git`.

To obtain the source code, run `git clone` the repo to your hard drive and set up a virtual environment by running `poetry` in the repo directory. For Windows:
```bash
python -m pip install --user poetry  # install poetry on your system
cd repo-folder                       # insert your repo directory
python -m poetry install             # create a virtual environment for the current directory
                                     # and install requirements from poetry.lock,
                                     # including development dependencies
```

# Pull requests
Pull requests are welcome. Please run `flake8` and `pytest` to ensure that your code will pass the automatic test first.

In order to send changes to the Cryptogull bot, it's best if you test them first. Here's a guide on how to do that.

### Steps to test the bot
1. Clone this repository if you have not already done so.
2. Create a `config.yml` in your cryptogull directory by copying from the provided `config.example.yml`. The `config.yml` is your personal file and it is listed in `.gitignore`, so you don't have to worry about accidentally sharing it through git.
3. Update your `Qud install folder:` if necessary in the `config.yml`
4. Log in to the [Discord Developer Portal](https://discordapp.com/developers/applications/) and create a new application. Call it something memorable, but this will not be the final name that the bot appears by in Discord.
5. Skip directly to the "Bot" tab of the application you created. Set the icon and username here. These can be changed later. Click the button to reveal the bot token. Copy this token into the `Discord token:` field at the top of your `config.yml` file in the Cryptogull source directory.
6. Turn on the "Server Members Intent" slider in the Bot tab.   
7. Create a private Discord server for yourself through the Discord client. The button is on the left under the list of servers you're in.
8. Grab the 'Client ID' from the 'General Information' tab of the Discord application you created (different from your bot token!)
9. Grab the permissions number you need from the 'Bot' tab of the Discord application you created. This should be 100352, which is the number created by checking the 'Send Messages', 'Attach Files', and 'Read Message History' checkboxes. If you're developing features that use higher permissions, check those permission boxes as well and use the permissions number created by doing that.
10. Craft a URL to join the bot to the server. The format is `https://discordapp.com/api/oauth2/authorize?client_id=xxxxxxxxxxxxxxxxxx&scope=bot&permissions=y` where the `x`s are the number from **step 7**, and `y` is the number from **step 8**.
11. Go to the URL to join your bot user to the new server. Accept any prompts.
12. Run `bot.py`. It will load the bot token from `config.yml` and connect to Discord, appearing in the server you added it to.

If you want to test character code decoding, there's a whitelist of channels in `config.yml`. Add yours there. The bot shouldn't listen to itself, but just in case, add the bot user ID to the 'Users to ignore' list. To get these IDs, just turn on 'developer mode' in the Discord client, under User Settings->Appearance. Then right click on anything to get its ID.
