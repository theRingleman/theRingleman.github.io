---
layout: post
title:  "RCPT-TRCKR - My Sinatra Final Project"
date:   2016-06-05 13:56:00 +0000
---


## What is this?

I wanted to create an app that I would actually use for this assessment. I wanted it to also be something that I would be interested in coming back to down the road and adding more functionality to it. I also wanted it to be something that others would find useful. So after a few days of trying to figure out what I wanted, I decided that I would do some form of personal finance app. This is RCPT-TRCKR.

## What it does.

This app allows users to create an account and then add their receipts from whatever store that they like, enter the items they purchased and the app will keep track of all of them. The user can view all of the stores that they have been to, and each individual store view has a list of every receipt from that store. The user is able to update all information about the receipts, items, and store. As well as delete everything of course.

## How I built it.

The hardest part of this whole application for me was setting up the relational database. I initially thought that I had everything right on my first run though and I was way off.

I have four different models: user, item, receipt, and store. I wanted the user to have many receipts, items, and stores. The receipts were going to belong to a user. The items were going to belong to a user and receipt, and the stores were going to have many users through a join table.

I first thought that I was going to have several join tables to accomplish what I was going to do and I just confused myself. The good thing about learning all this was that I found a new flow for my coding that really helped me, and if it weren't for the [tux](https://rubygems.org/gems/tux) gem I think that I would have really pulled my hair out. I really like the fact that I was able to dive right into my database and manipulate everything in there. So my new flow was add some code that I though would work, then hop into tux and test it, find out that I was wrong with something small, go back and fix it, then back into tux to verify my fix. I found out that I did this a lot more than just setting up the database relationships.

So, after two days of great frustration I finally asked a Learn instructor, and everything that he said was very helpful but I was still confused. So on the third day I went back and read some old lessons and had the proverbial AHA moment. I took to the white board, literally wrote out how my database tables should be set up, and found that I just used the receipt as my only join table.

```ruby
User
  has_many :receipts
  has_many :stores, through: :receipts
  has_many :items, through: :receipts

Store
  has_many :receipts
  has_many :users, through: :receipts

Receipt
  belongs_to :user
  belongs_to :store
  has_many :items

Item
  belongs_to :receipt
```

My object relationships finally worked! And of course, it was much easier than I thought it would be.

Once that was working it was just running through Sinatra and getting my pages set up the way that I wanted and adding features.

On thing that tripped me up was connecting CSS to my app. I went through the standard way of linking a stylesheet through an assets folder like I was previously used to and Sinatra wasn't having any of that. I found out that Sinatra looks for any static files in a public folder thanks to stack overflow. So all I had to do was put my CSS file in that folder and link to it.

``` html
<link rel="stylesheet" href="main.css" type="text/css">
```

I fought that whole thing for a few hours, but I learned a good lesson here too, Stack Overflow is my best friend in this situation and I shouldn't wait until I get frustrated to look it up.

I did want to add a front end to my so it looked presentable. I added the [Materialize](http://materializecss.com/) CSS framework and played around with that for the first time. I am really happy that I did because it broke me out of my comfort zone with Bootstrap and I found some really nice things that I like about Materialize. You will have to look at my forms, it is so much fun!

## Wrap Up

I had so much with this app! This is where I started to actually feel like I could build something of value, and started to feel like a real web developer. It was awesome thinking of a feature and just hacking away until I was able to implement it.

Here is my [github repo](https://github.com/theRingleman/rcpt_trckr) incase you would like to look at my code. Thanks for taking the time to read this!

