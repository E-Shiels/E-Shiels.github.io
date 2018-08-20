---
layout: post
title:      "Developing My Ruby CLI Data Gem"
date:       2018-08-20 16:36:03 +0000
permalink:  developing_my_ruby_cli_data_gem
---


I recently finished development on my Ruby CLI Data Gem project. I decided to develop a gem that would access the fantasy football rankings and data found at [FantasyPros.com](https://www.fantasypros.com/nfl/rankings/consensus-cheatsheets.php). You can check out the source code [here.](https://github.com/E-Shiels/fantasy_football_lookup)

![](https://preview.ibb.co/mkVYLz/snip1.png)

FantasyPros provides a lot of data, but the two pieces that I felt were most important to include in my gem were the rankings, and the draft pick data. 

My first step in the development of this project was determining the information that I would display. I decided to display all of the information available on the main rankings page, except for the standard deviation information. I then wrote out a list of commands that I wanted the CLI to accept. I wanted the gem to be able to print out the data of the top-ranked players, as well as search for a specific player. I also decided that I wanted there to be a command that would explain some of the fantasy football terms for people who are new to the game.

After planning that out, I started to figure out my class structure. I ended up with just a player class and a CLI class. The player class would be in charge of scraping the website data and searching for players, and the CLI class would handle pretty much everything else.

At this point, I felt like things were planned out enough for me to start some programming. I began by writing out the CLI flow and commands. I defined a method called "call" that would run the methods that scrape the players, welcome the user, and run the menu. 

I then decided to switch gears and start programming the player class. I ended up spending several hours figuring my scraping methods. Each row in the player ranking table has the class `player-row`, so I decided to iterate over the rows, instantiate a  player, and create an array that will contain all of the row data. Next, it iterates over the row data and adds it to the row data array.  Finally, it sets the players attributes equal to various pieces of data from the row data array and adds the player to an array of all players. I was able to assign most of the attributes easily because the row data array contained individual items for that data. However, the player name, team, and position were more difficult. That data wasn't on its own, so I scanned with a regular expression.

![](https://image.ibb.co/mTnSVz/snip2.png)

Now that I'd finished the player scraping, I decided to switch gears again and finish up the CLI. I used an if statement to check the input. When the method is called, and after any command is completed, it puts a list of commands. When the input is `exit`, the CLI puts a goodbye message and ends the loop. When the input is `explain`, it puts an explanation of the different fantasy football terms used. When the input is `search`, it puts a message asking for the player name that they want to search for. If then runs a Player method that checks if the player exists, and if it does, it puts the player rankings and data.

The final CLI method is the method to return the top-ranked players. If the input is `top-25, top-50, top-100, or top-all`, it needs to return the top 25, 50, 100 and all players respectively. Instead of checking for top-25, top-50, and top-100 individually, I have it remove the `top-` with `.gsub` and setting `n` equal to the remainder of the input. It then puts each player in the first(n). `Top-all` puts all of the players.

![](https://image.ibb.co/c6P50z/snip3.png)

Developing this gem was certainly not easy, but I feel that it was a worthwhile challenge. You can check out the full source code [here.](https://github.com/E-Shiels/fantasy_football_lookup)
