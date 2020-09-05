# yearn-faq-bot
Implementation of Discord bot for answering yEarn related questions.  

The bot has a categorized predefined [list](#list-of-questions-currently-available) of most frequent questions.  
    
It offers search functionality to users in DM.  

When asked a question in DM, the bot will try to find the best possible match from the known questions.  

This is the list of [commands](#known-dm-commands) available in DM with the bot.

In public channels the bot is only meant to answer predefined questions, with the command **!FAQ question *questionNumber***, e.g. **!FAQ question 7**.  
It can also use [aliases](#list-of-aliases-currently-available) for a question to post an answer in public channel, e.g. **!FAQ gas price**.    

The answers are built using Discord [Embeds](https://discordjs.guide/popular-topics/embeds.html) for pretty print, embedding links and adding images.

# Usage in channels
The bot is triggered by the prefix **!faq** in channels.  
The bot can answer predefined questions either by their question number of by alias.  
Examples:  
**!faq question 1**  
**!faq gas price**  

The list of all [questions](#list-of-questions-currently-available).  
The list of all [aliases](#list-of-aliases-currently-available).  
You can also get the latest aliases from the bot by sending him a DM **aliases**

# Usage in direct messaging

The bot is intended to be used mainly in direct messaging.
It has a list of predefined commands which can be browsed if **help** message is sent to the bot.

Additonally to known commands, the bot **can be asked a custom question (detected by a question mark at the end of the message)**. It will search for best possible match in the list of known questions.

## Known DM commands

**help**  
Displays the list of known commands


**list**  
Lists all known questions

**categories**  
Lists all categories of known questions


**category categoryName**  
List all known questions for a given category name, e.g. **category YFI**

**question questionNumber**  
Shows the answer to the question defined by its number, e.g. **question 7**

**search searchTerm**  
Search all known questions by given search term, e.g. **search YFI price**

**aliases**  
Lists all known aliases

**subscribe gas safeGasPrice**  
Subscribe to the bot so it will inform you if the safe gas price fall bellow the given safeGasPrice threshold, e.g. **subscribe gas 70**

**show chart [period]**  
Shows the YFI price chart for the given period, e.g. **show chart 24H**  


**Or Ask the bot any question and it will try its' best to find a match from the known questions**
  

# How to add a new question&answer?
If you find a question missing, please submit it via pull request keeping in mind the following:

1. Add the question itself to the questions folder with its dedicated file with next available number e.g. 20.txt  
2. Add the question answer in JSON format to the answers folder with the same number, e.g. 20.json. The JSON format corresponds to Discord [Embeds](https://discordjs.guide/popular-topics/embeds.html) to support rich text, images and embedded links.  
3. Optionally categorize the question to make it findable by category in categories/categories.json file. If you strongly believe the question needs a dedicated category, feel free to add a new one.  
4. If you want the new question to be available via one or more aliases, add it to the file categories/aliases.json  
5. If the question should have an image, add the image to images folder and reference it from the answer json. Only one image per reply is supported with Discord Embeds.
