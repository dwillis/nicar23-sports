# Bringing data journalism to the sports section

Materials for this NICAR 2023 session.

* Matt Waite, University of Nebraska
* Derek Willis, University of Maryland
* [Rina Torchinsky](https://github.com/rinatorch/jour479x_fall_2022/blob/main/presentations/presentation2_new.Rmd), University of Maryland
* MaryJo Webster, Star Tribune (in absentia)

### Resources

* [Sports DataVerse](https://sportsdataverse.org/)
* [Sports Data Analysis and Visualization](https://www.thescoop.org/sports/)
* [Using R Packages to get data](https://www.thescoop.org/sports/usingpackages.html)

### Examples

* [Behind the Minnesota Vikings' Wild Season](https://www.startribune.com/a-look-at-the-data-behind-the-minnesota-vikings-wild-unpredictable-season/600241956/)

We wanted a story that would especially appeal to our digital readers that heavily used data and graphics to look back at the Vikings' crazy season, just as they were heading into a playoff game. The biggest piece on this story were the play-by-play win probability charts, which is from data that you can pull using the espnscrapeR package. (My [video tutorials](https://sites.google.com/view/mj-basic-data-academy/intro-to-r/getting-nfl-data?authuser=0) show how to do that for one or multiple games.)

I also used play-by-play data downloaded with the espnscrapeR package to look at the point differential at the end of each quarter. The play by play data is super useful because it not only shows every play, but also has a record for the end of each quarter, the two-minute warnings and you can also find the start of overtime.

* In November, we also published [this data-heavy piece on the Vikings](https://www.startribune.com/9-charts-that-show-the-minnesota-vikings-stunning-turnaround-from-last-season/600227084/). It also leaned heavily on the win probability data. We also used some NFL NextGen stats to look at average separation stats for Justin Jefferson. You can get that data with this little snippet: 

```
receiving_next_gen <-  load_nextgen_stats(
  seasons = TRUE,
  stat_type = "receiving",
  file_type = getOption("nflreadr.prefer", default = "rds")
)
```

And then we also got passing stats on Kirk Cousins that show how often he was throwing into tight coverage (known as "aggressiveness")
You can get that data with this: 

```
passing_next_gen <-  load_nextgen_stats(
  seasons = TRUE,
  stat_type = "passing",
  file_type = getOption("nflreadr.prefer", default = "rds")
)
```

* [Justin Jefferson piece](https://www.startribune.com/justin-jefferson-minnesota-vikings-statistics-all-pro-mvp-randy-moss/600247729/?refresh=true), February 2023:  
Most of this is just high-level stuff taken from various websites, but there are two pieces where we pulled data from an API using R. The main one is the bubble chart that shows how Jefferson led the team on offensive yards (There is a nifty package called "[packcircles](mimestream://messagethread/p448483/message/p511829?UUID=52FF0A60-4ECD-493C-B780-C97901E30DF2&loadRemoteResources#https://r-graph-gallery.com/305-basic-circle-packing-with-one-level.html)" that works with plotly package to make a bubble chart. The one in our story was made with other technology, though).  I also pulled the receiving yards per game data from the espnscrapR package, play by play data.

* [What makes a fair trade for a first overall pick? Analysis of NHL Entry Draft Pick Values in Trade](https://jetsonku.github.io/sportsdatablog/2022/12/05/nhl-draft-pick-value/)
* [There's Only One Caitlin Clark. Who Else Has "Clark-like" Stats?](https://herhoopstats.substack.com/p/theres-only-one-caitlin-clark-who)
* [Fewer Players Feast on Free Throws](https://herhoopstats.substack.com/p/ncaa-wbb-2022-free-throw-feast)
* [Recreation Deserts in Maryland](https://github.com/rinatorch/jour479x_fall_2022/tree/main/presentations)
