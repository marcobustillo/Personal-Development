# Discord Bot
**Discord Bot** to automate, simplify tasks in discord.

## Table of Contents
- [Discord Bot JS](#discord-bot-js)
- [Discord Bot Python](#discord-bot-python)


## Discord Bot JS
**Discord Bot JS** is a powerful nodejs module that allows you to interact with the Discord API

### Table of Contents
- [Installation](#discord-bot-js-installation)
- [Get Started](#discord-bot-js-getstarted)

### Installation
- You need to install Node JS 6.0.0 or newer
- After installing Node JS you may now use `npm` to install discord.js module
- First go to your desired directory to create a bot
- Go to the directory and make a folder of the name of your bot (SpotifyDiscordBot)
- Go inside on your newly created folder
- run the following options on your folder
  - **Without voice support:** `npm install discord.js`
  - **With voice support:** `npm install discord.js node-opus` (**Note:** node-opus is a another nodejs module)
  - **With voice support:** `npm install discord.js opusscript` (**Note:** opusscript is another nodejs module)
- Once installed we can now proceed to Get Started

### Get Started
We are tacking this note/tutorial expecting that you have knowledge in Javascript.
I recommend you first need to learn about Javascript. If you dont know JS but would like to learn about it, here are a few links to help you get started.(Skip if you have prior knowledge)
- [Codeacademy](https://www.codecademy.com/learn/introduction-to-javascript)
- [Nodeschool](https://nodeschool.io/)
- [W3Schools](https://www.w3schools.com/js/)
- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [Google](https://www.google.com.ph/search?q=javascript+tutorials&rlz=1C1CHBF_enPH808PH809&oq=javascript+tutorials&aqs=chrome..69i57.2544j0j1&sourceid=chrome&ie=UTF-8)

Lets Begin:
- First you need to setup the actual discord bot application via Discord's Website
  - Open the [Discord Website](https://discordapp.com/login) and login.
  - Hover over the "Developers" drop-down menu and click on the [Developer Portal](https://discordapp.com/developers/docs/intro) link.
  - On the header click on the [Application](https://discordapp.com/developers/applications) link.
  - Click on the "Create an application" button.

  You should see something like this.

  ![discord1](../../../pictures/bot/discordcreate1.png)

  You can optionally enter a name, description, and avatar for your application here. Once you've saved your changes, you can move on by selecting the "Bot" tab in the left pane.

  ![discord2](../../../pictures/bot/discordcreate2.png)

  Click the "Add Bot" button on the right and confirm the pop-up window by clicking "Yes, do it!". Congratulations, you're now the proud owner of a shiny new Discord bot! You're not quite done, though.
- Next, You need to get the bots token. What is a token? A token is your bots password. It's what uses to login to discord. **NOTE:** Never Share your bots token. If someone gets ahold of your token basically its also their bot now.
- After creating a bot user, You'll see something like this:
![discordtoken](../../../pictures/bot/token.png)
- If you want to get your token click the Reveal Token.
- If you want to generate a new token click Regenerate
- Next, You need to invite your bot in your discord server

- Next you need to create a `index.js` in the root directory of your bot folder.
- Once you have created a file
