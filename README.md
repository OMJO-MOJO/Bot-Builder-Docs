# Documentation for Bot Builder

## Set up the project
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
   features: ["music"], // optional; default: []
   logChannelId: "12345", // optional; default: ""
});
```
Note: The features in the Bot Builder options is the list of available features to select from.

## Create a bot
``` js
BotBuilder.create(userId, {
  username: "Bot's Username", // required
  description: "This is an example of the bot's description", // optional; default: ""
  features: ["music"], // optional; default: []
  token: "BOT_TOKEN", // optional; default: fetches one from the token list in the token's path
});
```
Note: The features in the Create options is the features that the user selects for their bot.

## Edit a bot
``` js
BotBuilder.edit(userId, {
  username: "New username", // optional; default: current username
  description: "New Description", // optional; default: current description
  features: ["New Feature"], // optional; default: current features
});
```
Note: If a username, description and/or features is not passed through, the Bot Builder will not update it and use the existing options

## Delete a bot
``` js
BotBuilder.delete(userId);
```









