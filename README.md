# Discord.js v13 for replit
A discord.js v13 bot set up for replit

[Click here to go to replit](https://replit.com/)


# How to use Discord.js v13 in Replit?

## Updating Node.js v12 to Node.js v16 in Replit

Execute this script on the shell to install node.js v16:
```
npm init -y && npm i --save-dev node@16 && npm config set prefix=$(pwd)/node_modules/node && export PATH=$(pwd)/node_modules/node/bin:$PATH
```

Create a `.replit` file to execute node from the shell instead of the console.
```
run = "npm start"
```

Now, add a code to `package.json` file
```js
  "scripts": {
    "start": "node ."
    }
```

If you had packages like discord.js v12 or sqlite before,please reinstall them.
```
npm uninstall discord.js && npm i discord.js
```

### Code for the discord bot
```
const { Client, Message, MessageEmbed } = require('discord.js')
const client = new Client({
    partials: ["MESSAGE", "CHANNEL", "REACTION"],
    intents: 32767,
});

module.exports = client;

const config = require('./config.json')
const prefix = config.prefix
const token = config.token


client.on("ready", () => {
    console.log(`${client.user.tag} is ready!`)
    client.user.setActivity(`${prefix}help ~ test`)
});


client.login(token)
```


**You can run the code now!**
