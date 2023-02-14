Grep Commands:

grep -rl 

```
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/lab 4 real/docsearch/written_2 (main)
$ grep -rl "frightening"
non-fiction/OUP/Berk/CH4.txt
travel_guides/berlitz2/Algarve-Intro.txt
travel_guides/berlitz2/Algarve-WhereToGo.txt
travel_guides/berlitz2/Boston-WhereToGo.txt
travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
travel_guides/berlitz2/Cancun-WhereToGo.txt
travel_guides/berlitz2/Cuba-WhereToGo.txt
```
This command searches recursively and lists all the files that contain the word frightening. This can be useful if you want to find a specific word in a bunch of files and directories. 

```
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/lab 4 real/docsearch/written_2 (main)
$ grep -rl "candid"
non-fiction/OUP/Abernathy/ch3.txt
non-fiction/OUP/Abernathy/ch7.txt
non-fiction/OUP/Castro/chL.txt
non-fiction/OUP/Fletcher/ch10.txt
non-fiction/OUP/Kauffman/ch1.txt
non-fiction/OUP/Kauffman/ch3.txt
non-fiction/OUP/Kauffman/ch4.txt
non-fiction/OUP/Kauffman/ch6.txt
non-fiction/OUP/Kauffman/ch7.txt
non-fiction/OUP/Kauffman/ch8.txt
travel_guides/berlitz1/HistoryMadrid.txt
travel_guides/berlitz1/WhatToLasVegas.txt
travel_guides/berlitz1/WhereToItaly.txt
travel_guides/berlitz1/WhereToMadrid.txt
travel_guides/berlitz2/Boston-WhereToGo.txt
```
This command searches recursively and lists all the files that contain the word candid. Basically it starts at the directory it was called in and it goes to each of the sub directories and all their files and searches to see if it contains the word. The output shows all the files in written2 that contain the word candid. 

grep -n

```
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/lab 4 real/docsearch/written_2/travel_guides/berlitz2 (main)
$ grep -n "fun" California-WhereToGo.txt
169:The crazed and pinnacled surface of the salt-caked lake bed has earned it the nickname of Devil’s Golf Course. Take a walk out across that glaring expanse of baked salt — the atmosphere of desolation is almost exhilarating. If you look closer at the salt under your feet, you’ll discover that the expansion of the crystallizing mineral has heaved it into bizarre funnels, swirls, and other intricate patterns.
175:The city of Las Vegas grew out of a stopover at a natural oasis, which burgeoned after Nevada’s legalization of gambling in 1931. Today, visitors converge on Vegas from all over America. Many are still here for a bit of fun and titillation, and to lose a few bucks at roulette or blackjack, but Las Vegas now touts itself as a family destination.
```
This command lists the line number of where a specific word exists in a file. The output shows the line number first and then the entire line listed out for you. So in this example the word "fun" is located on these lines in the following file. This can be useful if you want to figure out which line number contains the word you are looking for. 

```
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/lab 4 real/docsearch/written_2/travel_guides/berlitz2 (main)$ grep -n "weather" California-WhereToGo.txt
68:Beside the Plaza is Monterey’s Fisherman’s Wharf. Like San Francisco’s, it is a collection of souvenir shops and restaurants on the dock, offering a great view across the boats in the marina. The fish on sale is most definitely fresh, but alas, no longer abundant enough to keep Cannery Row going as more than a weather-beaten curiosity. The famous sardine fisheries finally closed down in the 1940s as a result of over-fishing, but the waterfront district of timbered canneries, immortalized by the novelist John Steinbeck as “a poem, a stink, a grating noise, a quality of light, a tone, a habit, a nostalgia,” has found a new lease on life today as a tourist attraction with souvenir shops, delightful cozy boutiques, and artists’ studios.
```
This command looks through the file to see if the specific word exists and every time it exists it returns the line number along with the entire line. In this case it is looking for the word "weather". This can be useful if you want to find a specific line in which the word exists. 


grep -v 
```
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/lab 4 real/docsearch/written_2/travel_guides/berlitz2 (main)
$ grep -v "a" Bahamas-History.txt


A Brief History
The 20th Century

```

This command looks throuh the file for a particular word and it inverts it so that all the lines that do not contain the word are returned instead. For exammple in this case it was looking for "a" and it reutnred all the words that do not contain a. It is important to notice that the case is not important. 

```
$ grep -v "a" Berlin-History.txt 




A Brief History
The Third Reich

```

This command looks through the file for a particular word and it inverts it so that all the lines that do not contain the word are returned instead. This example was run on a different file from the one before. It can be useful if you want to find if any lines in a file do not contain a word that they are supposed to. 

grep -E
```
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/lab 4 real/docsearch/written_2/travel_guides/berlitz2 (main)
$ grep -E '[0-9]{4}' Berlin-WhatToDo.txt
Another long-standing Berlin tradition, at its heyday in the 1920s, satirical cabaret has always, by its very nature, had to struggle for its existence. Berlin has seemed to provide the necessary raw material, a perennially turbulent history to which reunification has not put a stop. Two survivors among the countless fly-by-nights are Die Stachelschweine (The Porcupines, Europa-Center) and Die Distel (The Thistle, Friedrichstraße 101). However, unless your German is excellent and you have an in-depth understanding of the political scene, this kind of cabaret will be almost impossible to follow.
Berlin’s sports facilities are second to none, thanks to the huge program of building that took place as part of the city’s bid for the 2000 Olympics. There are over 1,500 sports venues in the city, most impressive of which are the Max-Schmeling-Halle and the Velodrom (both in the Prenzlauer Berg district).
The ultimate in professional football will be seen when Berlin hosts the final of the Soccer World Cup in 2006, for which the Olympic Stadium is undergoing a massive program of refurbishment. The annual Six Day Cycle Race has been held every January since 1997 at the Velodrom, while the Max-Schmeling-Halle draws basketball fans by the thousands to see the home team, Alba Berlin, take on the opposition. International tennis tournaments are held at the Rot-Weiß club. Horse-racing enthusiasts can check out German equine form at the Galopprennbahn Hoppegarten and last, but by no means least, the Berlin Marathon can be enjoyed from the sidelines throughout the city every autumn.
```

This command looks for a specific pattern in a particular file. In the example above E is followed by '[0-9]{4}' which means that the command is looking for any 4 digit string that contains any value between 0 and 9. The return value of the command is all the lines that containt he following pattern. This can be useful in the following way if you want to find and dates. 

```
vkom5@DESKTOP-CL5JJTR MINGW64 ~/Downloads/lab 4 real/docsearch/written_2/travel_guides/berlitz2 (main)
$ grep -E '[a-z]{17}' Berlin-WhatToDo.txt
If you want to take back an edible souvenir, make sure you know your country’s regulations governing the import of certain types of food. Among the pastries and cakes which travel best are Lebkuchen (gingerbread), Spekulatius (spiced Christmas cookies), and marzipan. KaDeWe’s Feinschmeckeretage offers 500 different breads, and 1,500 different types of cheese plus rare eastern delicacies, exotic teas, handmade chocolates, and Beluga caviar. Berlin has no local wine, but plenty of wine shops to satisfy all connoisseurs of the best Rhine, Mosel, and Baden Württemberg vintages.
```
This command looks for a specific pattern in a particular file. In the example above E is followed by '[a-z]{17}' which means that the command is looking for any 17 length string that contains any value between a and z. The return value of the command is all the lines that containt he following pattern. This can be useful in the following way if you want to find a really long word in a file. 

For all of my command lines that I found I used chat gpt. I used the following promt to guide it to give me these examples:
```
can u list 4 alternate ways to use the grep command  and make sure they are interesting and unique  in bash 
```
