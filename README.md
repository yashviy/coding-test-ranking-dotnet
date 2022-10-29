# Challenge: Ad quality management service

[![Build Status](https://travis-ci.org/idealista/coding-test-ranking-dotnet.svg?branch=main)](https://travis-ci.org/idealista/coding-test-ranking-dotnet)

This repository contains a partially developed API to develop a service that is responsible for measuring the quality of ads. Your goal will be to implement the user stories described below.

The assumptions are based on a hypothetical *ads quality management team*, which requires a series of automatic checks to classify the ads based on a series of specific characteristics.

## User Stories

* As head of the ad quality management team, I want to assign a score to an ad so that idealista users can sort ads from most complete to least complete. The ad score is a value between 0 and 100 that is calculated taking into account the following rules:
  * If the ad does not have any photos, 10 points will be deducted. Each photo in the listing earns 20 points if it's a high-resolution (HD) photo, or 10 if it's not.
  * That the ad has a descriptive text adds 5 points.
  * The size of the description also earns points when the ad is about a flat or a chalet. In the case of flats, the description earns 10 points if it has between 20 and 49 words or 30 points if it has 50 or more words. In the case of chalets, if it has more than 50 words, add 20 points.
  * That the following words appear in the description add 5 points each: Bright, New, Central, Renovated, Penthouse.
  * That the announcement is complete also contributes points. To consider a complete advertisement, it must have a description, at least one photo and the particular data of each type, that is, in the case of flats it must also have the size of the house, in the case of chalets, the size of the house and of garden. In addition, exceptionally, in garages it is not necessary for the advertisement to have a description. If the ad has all of the above data, provide another 40 points.

* As a quality manager, I want users not to see irrelevant ads so that the user always sees quality content on idealista. An ad is considered irrelevant if it scores less than 40 points.

* As a quality manager I want to be able to see the irrelevant ads and from what date they are irrelevant to measure the average quality of the content of the portal.

* As an idealista user, I want to be able to see the ads ordered from best to worst to easily find my home.
## Important considerations

In this project we provide you with a small *skeleton* written in .Net Core 2.2 (you can port it to Framework 4.X or another version of .Net core)

In said *skeleton* we have left for you to complete a [Controller] and a [Repository] in memory. You can create the classes and methods that you consider necessary.

**Data persistence is not part of the goal of the challenge**. If you are not going to use the skeleton that we provide, we suggest you simplify it as much as you can (with an embedded database, "persisting" the objects in memory, using a file...). **The design of a graphical interface is also not** part of the scope of the challenge, therefore you do not need to implement it.

**Note:** You are not obligated to use the provided project. If you prefer, you can use any other language, framework and/or library. You can even do without the latter if you consider that they are not necessary. What we give the most importance to is having a clean and quality code.

## Criteria of acceptance

* Code must compile and be executable :dancer:

* You must provide 3 endpoints: One to calculate the score of all the ads, another to list the ads for an idealista user and another to list the ads for the person in charge of the quality management department.
