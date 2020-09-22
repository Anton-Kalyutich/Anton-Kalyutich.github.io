---
layout: post
title:      "CLI Project: How I Made It Work"
date:       2020-09-22 12:36:44 +0000
permalink:  cli_project_how_i_made_it_work
---

I'll confess right away that my gem is quite simple and straight forward, but I guess it was the nature of the problem that made me go after bold solutions. I was trying to implement my variation of a random movie picker and assumed that the very cause of trouble is abundance of information and all kinds of sophisticated tools to browse through dozens and dozens of movies. So, the remedy should be as simple and direct as possible.

Initially, my plan was to get lists of movies from the three movie websites: "Rotten Tomatoes", "Metacritic" and "IMDb". My program would then randomly pick one movie from each list and offer them to the user, who then would be able to use menu options to get more info on each movie in my shortlist, or list them again, or exit. I thought I wouldn't allow the user to make another search and browse too much, as it's exactly how you get lost and never pick anything.

I had a choice of either scraping the info I needed, or getting it from APIs. I went for scraping as it was a technique somewhat fresher in my mind, even though I am now realizing I should've chosen API way. The tricky thing about scraping different websites is that they are formatted very differently, and you can't really be sure you'll have easy access to all the information you'd need. Most movie lists are organized in a way that you can only scrape basic info from the main webpage, and to obtain more details on each movie you need to go one level deeper - easier say than do as those extra links on each position are not always formatted the same way.

After joggling with many ideas in my head I decided I'd pick one website which already gives a decent pick to the user and simply scrape it n number of times. Each time I'd hit the website, I'd get a completely new option with exactly the same scraping accessability. I chose suggestmemovie.com. My program simply visits it 3 different times to give my user a choice of 3 movies to pick from. I do realize my program is very vulnerable since it won't work if the website is down or changes, or there's trouble loading stuff from this one soure. But hey, it works and I guess it's quite sufficient to pass all the requirements for the project.

By the way, my technical review is still ahead, and I'll be quite okay to make the whole thing again from scratch - this time, going via API path. But before doing so I'd want to get some feeback first. I can then go ahead and apply another approach. Let's see! 

As it currently stands, my program first greets the user and then immediatly hits the website with a random movie pick. It does it 3 times, but it can be any number of times, really. My program frexible enough to accomodate as many movie picks as needed. It scrapes all the info right away, as there will be no way to come back and get more information later. The user then is presented with a choice of 3 movies (just titles and realese years). The user can choose a number of the movie to get more info about, to list them again or exits. On the way out the program says 'goodbye'. As simple as that. I made a concious choice not to allow the user to scrape for more movies - the only way to do it would be to start the program again.

My classes are 1. CLI, which is responsible for interaction with the user, 2. Movie class, which is not really doing much besides initializing the instances with a bunch of properties and then storing them, and the 3. Scraper class, which retreaves all the info. The #menu method within the CLI class is designed as a loop only exiting upon a command from the user. Otherwise, you just go back and forth from the list of picked movies to a more detailed description of each.

Not sure what else could be of interest here. My program works the way I want it to, and I don't think I'll be changing it much before I hear from Flatiron guys. And then let's see - maybe I'll get to implement a completely different appoach to the problem. That's gonna be fun anyways, looking forward to it.
