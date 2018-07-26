---
layout: post
title: symphony with symfony
date: 2009-05-21
tags: ["symfony","web-development"]
---

OK the guys at neevtech told me to 'do' symphony. So what I did was start learning symfony. There is an excellent online resource for symfony: [http://www.symfony-project.org/doc/](http://www.symfony-project.org/doc/ "Symfony documentation")

I(as a newbie) will recommend that you use it with wamp server to right away get down to business. WAMP .well nothing as good as WAMP:[ http://www.wampserver.com/en/](http://www.wampserver.com/en/ "WAMP homepage")

Another link would be:[ http://trac.symfony-project.org/wiki/SymfonyOnWAMP](http://trac.symfony-project.org/wiki/SymfonyOnWAMP "Symfony on wamp") but I think it refers to the old wamp release(but no problem ;)  ).

Steps I would suggest that you take are:

1. Get wamp from it's website. Install it.

2. If you now execute wamp and if you get a white half pie symbol-err..a tachometer(it will go from red to yellow don't worry) on your system tray then you are good for the start.

(i)Else(if it's red or yellow): you need to check which service is running(apache or MySQL) and which is not. Click the tray icon-go to Apache(or MySQL-whichever is the culprit) and go to service menu...See if its running(or if it's the problem, _it's asking to be run_ )

(ii)As a last ditch edit the line in httpd.conf(available in the Apache menu from the tray icon) that says listen 80 to "listen 8080"(without the quotes of course) also change my.ini(from the mysql menu) so that [MYSQLd] points to port 3307(or just damn search for 3306 and replace with 3307)[refer these for more help[ http://www.azazia.com/kb/entry/7/](http://www.azazia.com/kb/entry/7/ "azazia- wamp help") OR  [http://www.wampserver.com/phorum/read.php?2,34885,page=2](http://www.wampserver.com/phorum/read.php?2,34885,page=2 "wamp forum") ]

That's all I can help in debugging ;)

3. In the wamp menu go to php -> PHP extensions and click php_xsl and see to it that php_pdo_sqlite is already ticked. Don't worry if it throws quirks/errors at you-play along...You will have to restart the server(or exit and start again wamp) --thing to note there are two php.ini( one is in wamp/bin/php/php5.2.x and other in wamp/bin/apache) so if you decide to do things manually check that both are set right.

4. Go to httpd.conf(how you ask? click icon->apache->httpd.conf ). And find a line :

`#LoadModule rewrite_module modules/mod_rewrite.so `

remove the leading hash # symbol to uncomment it.( this thingy caused a real pain when I was neck deep in my first symfony project)

5. ok...You are ready to go....Navigate to http://localhost:80(which is the same as http://localhost) or http://localhost:8080 (if you tinkered with httpd.conf in step 2)...if god shows mercy you'll get a nice wamp server screen...

6. Time to read tutorials(the first link i mentioned)....If you want to get right into I'll suggest first read up day 1 of the "jobeet" tutorial and then get back to "my first symfony project"

7. If you get stuck- get to #symfony@freenode.net and bother some really wonderful people.

(i) If you are getting problems with php....then do` php -i'more` on the command prompt/terminal- that will tell you all about your cause of php troubles.

note: you may get a warning somewhere along your first project or whatever saying that you should get a php accelerator(some apc)....just don't bother.

Phew that was a long post....I wonder why it was soooo big. Well I guess this blog is useful only for windooze users-sorry linux bros-right now I am stuck on a windooze platform.