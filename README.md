Compliment Bot
===============

A set of scripts to send compliments to someone at random intervals!

Requirements
------------

* [sqlite3][1]
* Some configured implementation of `sendmail` (e.g. [ssmtp][2])
* Some periodic scheduler, e.g. `cron`
* [bash][3]

Scripts
--------

* `initialize-db DATABASE_FILE`: Initialize the Compliment Bot database
* `insert DATABASE_FILE TABLE`: Insert a message into TABLE. Valid tables are
                                `tidbits` (sent on non-compliment days) and
                                `compliments`. Message read from standard input
                                ([this][4] may be helpful).
* `send DATABASE_FILE NAME ADDRESS`: Send a message randomly drawn from either
                                     `tidbits` or `compliments` to NAME at
                                     address ADDRESS. Meant to be made into a
                                     cron job.
* `send-initial DATABASE_FILE NAME ADDRESS SENDER`: Send an initial message
                                                    explaining Compliment Bot
                                                    and that SENDER has set up
                                                    periodic messages.

Note that there is essentially no error handling, and you have to make sure
you've populated the database with enough compliments and tidbits.

[1]: https://www.sqlite.org/
[2]: https://wiki.archlinux.org/index.php/SSMTP
[3]: https://www.gnu.org/software/bash/
[4]: https://en.wikipedia.org/wiki/End-of-transmission_character
