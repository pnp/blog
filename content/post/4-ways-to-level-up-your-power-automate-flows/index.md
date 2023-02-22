---
title: "4 ways to level up your Power Automate flows"
date: 2021-09-18T08:40:00-04:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Community post"]
images:
- images/Teams-status.png
tags: []
type: "regular"
---

## Intro 

A while back, I wrote about [How to use a custom connector in Power Automate](https://www.m365princess.com/blogs/2021-02-23-how-to-use-a-custom-connector-in-power-automate/) showing how easy you can create a connector to a cloud service that is not already in the very long list of connectors in Power Automate. I chose to create a connector for Spotify and connected a `Get_Current_Song` action with an IOT button and twitter. As a result, information about the song I would be listening to would be tweeted.

Now I stumbled upon a [really great blog post](https://www.loryanstrant.com/2021/09/16/how-to-display-the-currently-playing-spotify-track-as-your-teams-status-message/) by fellow MVP Loryan Strant who also used this Spotify connector to change the pinned message of your status in Microsoft Teams. To get the most value out of this post, go read Loryans post first- it is written with great clarity and also I love this guys' taste of music :musical_notes:! Also please understand his flow first. I love the idea and creativity! The result of such a flow looks like this:

![Teams-status.png](images/Teams-status.png)

While some would debate if this flow is necessary, I feel it shows that custom connectors are a great way to extend Microsoft 365. Also: #MusicWasMyFirstLove - case closed :)

However when reading this blog post, I saw some patterns that I often see in flows and that could be improved - and as I could already learn so much from Loryan, this time I hope to return the favor :)

Loryan created 13 actions and as I seem to be just more lazy than he is, therefore I thinned out his awesome idea to just 5-6 actions: This is what it looks like:

![flow-overview.png](images/flow-overview.png)

The result is about the same - just that I display also a message if I am currently not listening to music (yes, this happens!)

## Parse JSON

First thing I wanted get rid of was the Parse JSON action. While it is super powerful and lets you easily access properties of objects that you get as response, it is unnecessary sometimes: We can also write the flow without it if we take a look on how we can select properties and return their values in expressions.

To be successful with that, it is crucial to understand the JSON schema of the response we are interested in. Easiest way to achieve that:

a) copy the body of the output of that action, paste it into a code editor - I work with Visual Studio Code

![flow-output.png](images/flow-output.png)


b) we make sure that we select `JSON` as language - VS Code will then color everything nicely for us and highlight beginning and ends of objects for example

c) we have a look at the code. For the sake of better readability - this schema is about 450 lines long, I already collapsed two arrays called `available markets` - it's a long list of country codes in which a particular song is available. We don't need it here. If you aim to rebuild this, its highly recommended to copy the code from YOUR output, not from this blog post, as I shortened the code.

```json
        {
            "timestamp": 1631969547352,
            "progress_ms": 85903,
            "item": {
              "album": {
                "album_type": "album",
                "artists": [
                  {
                    "external_urls": {
                      "spotify": "https://open.spotify.com/artist/3CQIn7N5CuRDP8wEI7FiDA"
                    },
                    "href": "https://api.spotify.com/v1/artists/3CQIn7N5CuRDP8wEI7FiDA",
                    "id": "3CQIn7N5CuRDP8wEI7FiDA",
                    "name": "Run–D.M.C.",
                    "type": "artist",
                    "uri": "spotify:artist:3CQIn7N5CuRDP8wEI7FiDA"
                  }
                ],
                "available_markets": [

                ],
                "external_urls": {
                  "spotify": "https://open.spotify.com/album/7AFsTiojVaB2I58oZ1tMRg"
                },
                "href": "https://api.spotify.com/v1/albums/7AFsTiojVaB2I58oZ1tMRg",
                "id": "7AFsTiojVaB2I58oZ1tMRg",
                "images": [
                  {
                    "height": 640,
                    "url": "https://i.scdn.co/image/ab67616d0000b273894ae4df775c6b47438991af",
                    "width": 640
                  },
                  {
                    "height": 300,
                    "url": "https://i.scdn.co/image/ab67616d00001e02894ae4df775c6b47438991af",
                    "width": 300
                  },
                  {
                    "height": 64,
                    "url": "https://i.scdn.co/image/ab67616d00004851894ae4df775c6b47438991af",
                    "width": 64
                  }
                ],
                "name": "Raising Hell",
                "release_date": "1986-05-15",
                "release_date_precision": "day",
                "total_tracks": 12,
                "type": "album",
                "uri": "spotify:album:7AFsTiojVaB2I58oZ1tMRg"
              },
              "artists": [
                {
                  "external_urls": {
                    "spotify": "https://open.spotify.com/artist/3CQIn7N5CuRDP8wEI7FiDA"
                  },
                  "href": "https://api.spotify.com/v1/artists/3CQIn7N5CuRDP8wEI7FiDA",
                  "id": "3CQIn7N5CuRDP8wEI7FiDA",
                  "name": "Run–D.M.C.",
                  "type": "artist",
                  "uri": "spotify:artist:3CQIn7N5CuRDP8wEI7FiDA"
                },
                {
                  "external_urls": {
                    "spotify": "https://open.spotify.com/artist/7Ey4PD4MYsKc5I2dolUwbH"
                  },
                  "href": "https://api.spotify.com/v1/artists/7Ey4PD4MYsKc5I2dolUwbH",
                  "id": "7Ey4PD4MYsKc5I2dolUwbH",
                  "name": "Aerosmith",
                  "type": "artist",
                  "uri": "spotify:artist:7Ey4PD4MYsKc5I2dolUwbH"
                }
              ],
              "available_markets": [

              ],
              "disc_number": 1,
              "duration_ms": 310386,
              "explicit": false,
              "external_ids": {
                "isrc": "USAR19900334"
              },
              "external_urls": {
                "spotify": "https://open.spotify.com/track/6qUEOWqOzu1rLPUPQ1ECpx"
              },
              "href": "https://api.spotify.com/v1/tracks/6qUEOWqOzu1rLPUPQ1ECpx",
              "id": "6qUEOWqOzu1rLPUPQ1ECpx",
              "is_local": false,
              "name": "Walk This Way (feat. Aerosmith)",
              "popularity": 69,
              "preview_url": "https://p.scdn.co/mp3-preview/c7a8010bbddcd0d793a832de76a24d2cae5ab497?cid=2e75e650d1e74b6a994734ed4aea2ef7",
              "track_number": 4,
              "type": "track",
              "uri": "spotify:track:6qUEOWqOzu1rLPUPQ1ECpx"
            },
            "currently_playing_type": "track",
            "actions": {
              "disallows": {
                "resuming": true,
                "toggling_repeat_context": true,
                "toggling_repeat_track": true,
                "toggling_shuffle": true
              }
            },
            "is_playing": true
          }
```

d) look for the properties you are interested in - for example we want to if a song is playing right now - we will find the `is_playing` property, which will either return `true` or `false`, which makes it perfect to put this into our condition:

![flow-condition.png](images/flow-condition.png)

The expression is `outputs('Get_Current_Song')['body']['is_playing']`.

Why is that? Let's deconstruct this: From the output of the `Get_Current_Song`, we are interested in the `['body']` and inside of this we want the value of the `['is_playing']` property

Now if we are also interested in the name of the song, we would do a quick search in that file for `name` and get four results:

1.  in line 14: this `name` property sits in the `artists` array, that consists of an `album` object and the `name` property here refers to the name of the artist of album, not to the name of the song that we are interested in.
2.  in line 221: this `name` property also sits in the `album` object and refers to the name of the album.
3.  line 235: this `name` property sits in the `artists` object and refers again to the name of the artist.
4.  finally, in line 432, we find the `name` property we were looking for; it sits in the `item` property.

Therefore, we will access the song name with:

`outputs('Get_Current_Song')['body']?['item']?['name]`

If we now also want to have the name of the artist, we get this with:

`outputs('Get_Current_Song')['body']?['item']?['album]?['artists][0]?['name']`

Wait, what? These are a lot of properties, so let's slow down for a bit to take a closer look:

1.  we get the `Get_Current_Song` action with `outputs('Get_Current_Song')`
2.  now we go ahead and with the `?` operator and select the first level property we are interested in: `item`
3.  next up is taking a look inside of the `item` property: what do we want to get here? It's the `album` property. We do this as before with `?` and the name of the property in `[]`: `?['album']`
4.  Inside of the `album` property we want to get the `artists` property and yet again we do this with `?` and the name of the property in `[]`: `?['artists']`
5.  Now remember that `artists` was an array? You can see this by the brackets `[]` in the code. We want to return the first element of this array, therefore we put a `[0]`. It's a zero, because arrays in JSON are zero-based, which means that the first element of an array has the index 0, the second one has index 1, and so on.
6.  Now that we returned that first element in the `artists` array (it's only one, but Power Automate will yell at you if you don't select just one element and instead return the entire array), we will go ahead and finally select the `name` property from it, which refers to the artist.

You see, it's all about understanding the underlying JSON schema and see, which properties are part of which objects. If you use the Parse JSON action, you don't need to write these expressions, but you face some disadvantages:

1.  you can now select from four `name` properties in your dynamic content - and need to select blindly
2.  You have no clue WHY you get four of those as you don't understand the data structure
3.  Parse JSON is yet another action which blows up your flow

## unnecessary Apply-to-each loops

You know that moment when you are creating a flow and and out of a sudden Power Automates automatically adds an Apply-to-each for you and you wonder why this happened? Also, you will face some issues later on? Wherever possible it's a good idea to avoid loops that are not necessary.

The fact that we didn't just parse the JSON output from our `Get_Current_Song` action but understood the JSON schema gives us an option to avoid a loop - we did not return an array of (one) artist, that triggered Power Automate to insert an apply-to-each loop, but we only returned the first element of the artist array - this way we don't need to loop over this one-element-array, which means that we got rid of another action!

## variables and expressions

Power Automate knows some nice actions for variables - the most important one is `initialize variable` - in Power Automate all variables need to be initialized (with or without value) before we can use them.

Now as we already skipped successfully the Parse JSON action and could also access artist name and song name without the use of variables but in expressions, I want to minimize the other initialize variables and compose actions from Loryans flow:

Instead of several actions and calculations to -- get the timestamp when the song started -- get the current time -- add the duration of the currently playing song to the current time, we could have one variable called `duration` with this expression:

`addSeconds(utcnow(),div(sub(outputs('Get_Current_Song')?['body']?['item']?['duration_ms'],outputs('Get_Current_Song')?['body']?['progress_ms']),1000))`

Explanation:

1.  This adds seconds to `utcnow()`, which is the current time.
2.  How many seconds? The return value from the subtraction of the duration in milliseconds `['duration_ms']` minus the `['progress_ms']` current progress in milliseconds
3.  With the div function this value is divided by 1000 as we want seconds instead of milliseconds.

## understand the API you are working with

The `Get_Current_Song` returns the LAST song that was played - and the `is_playing` property returns if the song is currently (still) playing or not. This means, that we need to distinguish between a song that played before I needed to turn off the music and a currently playing song. You might say, well, this doesn't really matter - but if we take a closer look to understand, which data is returned when, we would need to redesign our flow: The fact that we get an output of the `Get_Current_Song` even if the `is_playing` property is `false`, means that we don't get a `null` when our subsequent actions expect an object, a string, an array or anything else that is NOT `null`. Yet again, understanding what happens behind the scenes because we understand the output of an action will make it easier to create flows.
