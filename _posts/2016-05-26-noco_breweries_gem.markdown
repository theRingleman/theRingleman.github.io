---
layout: post
title:  "Noco Breweries GEM"
date:   2016-05-26 19:59:15 +0000
---


## Inspiration

When I learned that I had to create a GEM for the learn verified program I was both terrified and excited at the same time. I wasn't sure what I was going to create, or how I was going to go about it. I had a couple of choices that were rolling around in my head and I decided that I wanted to create something that I would actually use. I live in Northern Colorado, Fort Collins in fact, and one of the great communities that people have come to know and love about Colorado is our micro brewery scene.

From Denver to Boulder up to Fort Collins is often referred to as  the "Napa Valley of Beer". We have over six dozen breweries up and down the Front Range. The National Brewers Association chose Boulder as its location for its headquarters. Denver is host to the **Great American Brew Fest**, the largest brewery festival in the world according to *Guinness World Records*.

So I wanted to create a program that will look through the towns that are close to me and return their breweries along with information about each one. So that is exactly what I made.

## Objects

After some deliberation and figuring out what I wanted my program to do, I decided that I could write this all using four different classes:
  - CLI
  - Town
  - Brewery
  - Scraper

### Scraper

I had to find a good source of information to be able to put this app together, and this was not an easy task. There are a lot of websites that talk about the Colorado beer scene, but I wanted one that was central to where I lived, that had information about each brewery, and had a lot of different breweries to choose from. I eventually landed on the [Fort Collins Brewery Guide](http://www.fortcollinsbreweryguide.com).

I wanted the scraper to do the majority of the work but I didn't really want to have to worry about creating instances of it, so all the methods in it are class methods and its only job is to scrape the website and create instances of the towns and breweries.

So when this came to scraping the website I had a really hard time grabbing certain pieces of information. The address was a difficult piece of information to grab. Each brewery had its own page and the information about each brewery was in a simple unordered list. For example:

- Brewery Name
- Brewery Description
- Brewery Menu
- Brewery Address
- Brewery Phone Number
- Brewery Website

This seems like it would be very easy to scrape, but the big problem that I had was that if they didn't have the information about the brewery they would just leave it out like it is no big deal. The problem with this, is that I would scrape the list then have the info in an array and if they were consistent then i could just grab it like:

```ruby
brewery_list = site.css("list")
Brewery.name = brewery_list[0]
```
But when they are random with their lists, you have to get creative. I had to come up with a regular expression to grab just the address every time. Which after some research I found out was a whole hell of a lot easier said than done.

```ruby
brewery.address = brewery_info.grep(/\d{1,5}\s\w+\s\w+\s\w+/).find {|item| item.strip.split(" ").length < 6}.strip unless brewery_info.grep(/\d{1,5}\s\w+\s\w+\s\w+/).find {|item| item.strip.split(" ").length < 6} == nil
```
Now this works but I found out that many addresses can completely trump my regular expression, but for this simple app, this does what I need it to do.

So there were many problems along the lines of scraping but nonetheless it was fun to try and solve these issues. The biggest lesson that I learned when it came to scraping was how important it is to write really clean and well thought out HTML. If the developers of this website simply used classes to categorize their information then my scraping would have been much easier. I could have simply grabbed the css class inside Nokogiri and I would have had to write a lot less code. But I am sure the dev was not too worried about me scraping his site. :poop:

### Town

This object was the easiest of the four. I just wanted the town to simply have a name and have many breweries. I just had the scraper scrape over the list of towns and breweries, grab the town name and create a new instance of the town class. Then of course the class would store all instances made in an `@@all` class array so I could access them later.

### Brewery

This object was simple in idea and rather difficult in execution primarily because of the issues discussed above with the scraper. I wanted the brewery to have a name, description, website, phone number, menu, and address. I had to do some creative thinking to get all of this information though. The initial list on the website just lists the towns and then each brewery that belongs to that town, each brewery on this list is a link to an individual page that has the list of information about the brewery. So I scraped each url for the brewery and stored that with each instance of the brewery class, then when the user wants more information about that particular brewery, the scraper grabs that url and gets the information about the brewery and presents the user with that information.

### CLI

This object took me a lot of time and a lot of trial and error to get right. I am still not happy with how this has turned out and it needs a lot of refactoring. I have one method that is **35** lines of code! I know, shame on me... :sweat:

The good news is that I learned a whole ton :smile:. I leaned about nesting while loops and not getting trapped in an infinite loop while inside of another loop. This was really neat for me, and to be honest, I was nervous writing it that way but it works so I can't complain.

It was interesting for me to have to think about how a user would interact with the program, and that I would have to give constant directions or it would be very easy to get lost in a CLI.

## Overall

Overall, I am very happy with how the CLI turned out. I could see this being used in a web app where users want to find breweries near them and see what is on tap. It was a total eye opener for me to write something from scratch. I have to say that I had so much fun building this program but I can see so many ways to improve on it that I will be excited for furthering its development.


