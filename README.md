UrTStats
========

UrTStats is a real time global stats system for the game _Urban Terror_ <--- That's a cool FPS, seriously, try it !
We are collecting every servers status and aggregate them to generate cool stats. For example, you can view live the number of players online and what gametypes they prefer, etc.

You can try out the live version here : [www.urtstats.net](http://www.urtstats.net)

###Your stats are wrong! UrbanTerror.info says that there are xxx players online and not yyy !!
Well... While I'm doing my best to be sure the backend scripts are running properly, sometimes (or everytime) servers do not respond because they are "too busy", "send crap", "don't want to answer", "don't care", "hate me" or "have networking problems". 

###Want to contribute?
Cool, I'm happy to hear that! Depending on your abilities, you can send me feedback, suggest new cool things to statify or read the code and send pull requests ;)

### Want to run your own UrTStats?
#### Requirements 
* A Server with a decent php version
* php-rrd (`apt-get install php5-rrd`)

#### How to make it work ?
5 Steps _(I assume that you already grabbed a copy of the code)_:

1. Edit `./data/conf.ini` with your settings
2. Create directories for **each** workers on `./crons/slots/` (0, 1, 2,....)
3. Run all php scrips on `./init/` to create all .rdd files :)
4. Run `crons/masters.cron.php` once, to generate a server_list.json for the collector
5. Add `./crons/collector.cron.php` and `./crons/masters.cron.php` on your crontab :)

`*/30 *  *    *   * php /path/to/Urtstats/crons/masters.cron.php` **AND**
`*/5 *  *    *   * php /path/to/Urtstats/crons/collector.cron.php`

And That's all ! UrTStats is now providing stats. After that you'll need to setup the website, but it's not available yet.

### About me 
I'm blapecool ( [@blapecool](http://www.twitter.com/blapecool) ). 
You can contact me by mail (hello AT urtstats.net)

### Thanks to
* Barbatos for hosting me :)
