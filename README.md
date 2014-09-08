# AWK-hack

## Requirements

1. Awk
2. Nethack xlogfile

## Quick Start

1. Go fetch the "raw xlog" information for your username and save it to a file. For example:

[zomgreg xlog data](http://alt.org/nethack/player-all-xlog.php?player=zomGreg)

1. You want the parts only that look like:

    ```
version=3.4.3:points=2432:deathdnum=2:deathlev=5:maxlvl=5:hp=-2:maxhp=67:deaths=1:deathdate=20110305:birthdate=20110305:uid=5:role=Val:race=Hum:gender=Fem:align=Neu:name=zomGreg:death=killed by an arrow:conduct=3968:turns=1030:achieve=0:nconducts=5:nachieves=0:realtime=1403:starttime=1299319989:endtime=1299321420:gamedelta=1431:gender0=Fem:align0=Neu:flags=0    
version=3.4.3:points=5137:deathdnum=2:deathlev=11:maxlvl=11:hp=-2:maxhp=47:deaths=1:deathdate=20110309:birthdate=20110305:uid=5:role=Val:race=Hum:gender=Fem:align=Law:name=zomGreg:death=killed by a ghoul, while paralyzed by a monster:conduct=3968:turns=2846:achieve=0:nconducts=5:nachieves=0:realtime=23418:starttime=1299321773:endtime=1299648616:gamedelta=326843:gender0=Fem:align0=Law:flags=0
version=3.4.3:points=1286:deathdnum=0:deathlev=4:maxlvl=4:hp=0:maxhp=50:deaths=1:deathdate=20110309:birthdate=20110309:uid=5:role=Val:race=Hum:gender=Fem:align=Law:name=zomGreg:death=killed by a giant bat, while unconscious from rotten food:conduct=3968:turns=1440:achieve=0:nconducts=5:nachieves=0:realtime=1733:starttime=1299649461:endtime=1299651214:gamedelta=1753:gender0=Fem:align0=Law:flags=0
```

So make sure you cut out any of the markup if you're using curl or wget to fetch.

1. Run the script

    awk -f stats.awk <your file>
    
if your file is called 2014-09-08, you would execute it like this:

    awk -f stats.awk 2014-09-08
    
### Sample Output

```
➜  awkhack git:(master) ✗ awk -f stats.awk 2014-09-08

            [ 323 games ]

            [ Ascensions ]

Ascensions:               24 ( 7.430 %)
Average Turns/Ascension:  62102.6
Fastest Ascension:        34752
Slowest Ascension:        123889

            [ The Numbers ]

Total points:             108828117
Average Score:            336929
Maximum Score:            19285362
Maximum HP:               602
Max Level:                53
Average Level Reached:    11.68
Total Turns:              3608721
Maximum Turns:            123889
Average Turns per Game:   11172
Total Deaths:             297
Max Deaths:               2
```



