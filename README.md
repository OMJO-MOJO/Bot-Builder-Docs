![Build A Bot](https://cdn.discordapp.com/attachments/855212186041319455/1048180291614806106/BAB_Banner.png)
# Documentation for Bot Builder

## Set up the project
> The features in the Bot Builder options is the list of available features to select from.
``` js
// Import the package
const { Client, IntentsBitField, Partials } = require("discord.js");
const BotBuilder = require("BotBuilder");

// Create a discord client
const client = new Client({
   intents: [IntentsBitField.Flags.Guilds],
   partials: [Partials.Channel],
});

// Create the Bot Builder
const BotBuilder = new BotBuilder({
   client: client, // required
   botsPath: "./bots", // required
   tokensPath: "./tokens.txt", // required
   features: ["music"], // optional
   logChannelId: "12345", // optional;
});

client.login(config.token)
```

## Create a bot
When creating a bot, it will return a promise that responds with a Bot Instance and it will automatically start the bot, so no need to manually start the bot when created.
> The features in the Create options is the features that the user selects for their bot.
``` js
BotBuilder.create(userId, {
  username: "Bot's Username", // required
  description: "Bot's description", // optional
  features: ["music"], // optional
  token: "BOT_TOKEN", // optional; default: fetches one from the token list in the token's path
})
.then((botInstance) => {
   // rest of the code ...
})
.catch((err) => {
   // Returns an error message in string format
   console.log(err)
});
```
### Result of the create method
``` js
BotInstance {
   _config: {
      id: null,
      userId: '12345',
      username: 'username',
      description: 'description',
      features: [ 'features' ],
      token: '',
      iconURL: 'https://cdn.discordapp.com/attachments/855212186041319455/1011933282096648192/default-icon.png',
      timestamps: { username: 0, avatar: 0 }
   },
   _client: {
      // Normal Discord Client
   }
} 
```

## Edit a bot
> If a username, description and/or features is not passed through, the Bot Builder will not update it and use the existing options.
``` js
BotBuilder.edit(userId, {
  username: "New username", // optional; default: doesn't update username
  description: "New Description", // optional; default: doesn't update description
  features: ["New Feature"], // optional; default: doesn't update features
});
```

## Delete a bot
``` js
BotBuilder.delete(userId);
```









