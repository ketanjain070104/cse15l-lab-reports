# **LAB REPORT 3**
This report covers 4 interesting command-line options or alternate ways to use the command 'grep'
## **grep -n [Word] [File]**
**What does it do?**

It prints the line number of each match.

**How is it useful?**

It could be used when we have to locate a word repeating multiple times. We can pinpoint the location of the word. This option can also be useful if we need to reference a specific line number in a script or program.

**Example 1**

```
ketan@KINKY MINGW64 ~/Downloads/docsearch-main/technical
$ grep -n "Abdul" 911report/chapter-1.txt
8:    For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.
```

**Example 2**

```
ketan@KINKY MINGW64 ~/Downloads/docsearch-main/technical
$ grep -n "Hazmi" 911report/chapter-6.txt
311:                their part in the planes operation-Nawaf al Hazmi and Khalid al Mihdhar. Two more,
349:            In early March 2000, Bangkok reported that Nawaf al Hazmi, now identified for the
352:                departure even though he had accompanied Hazmi on the United flight to Los
356:                try to register Mihdhar or Hazmi with the State Department's TIPOFF watchlist-either
358:                Hazmi, too, had had a U.S. visa and a ticket to Los Angeles.
360:            None of this information-about Mihdhar's U.S. visa or Hazmi's travel to the United
```

Source [here](https://linuxize.com/post/how-to-use-grep-command-to-search-files-in-linux/)

## **grep -c [Word] [File]**
**What does it do?**

It prints the number of times a pattern occurs in the file.

**How is it useful?**

It could be useful when we need to quickly get a count of the number of occurrences of a specific pattern within one or more files.

**Example 1**

```
ketan@KINKY MINGW64 ~/Downloads/docsearch-main/technical
$ grep -c "Abdul" 911report/chapter-7.txt
44
```

**Example 2**

```
ketan@KINKY MINGW64 ~/Downloads/docsearch-main/technical
$ grep -c "is" 911report/chapter-1.txt
222
```

Source [here](https://linuxize.com/post/how-to-use-grep-command-to-search-files-in-linux/)

## **grep -r [Word] [Directory]**
**What does it do?**

It performs a recursive search for all files and directories within a specified directory, and searches for a pattern within those files. 

**How is it useful?**

 It can be useful when we need to search for a specific pattern within a large directory tree that contains many subdirectories.
 
 **Example 1**
 
 ```
 ketan@KINKY MINGW64 ~/Downloads/docsearch-main/technical
$ grep -r "Cochrane" biomed/
biomed/1468-6708-3-7.txt:        Medline and the Cochrane databases were used to identify
biomed/1471-2253-2-4.txt:        Cochrane Library (issue 4, 2001), Biological Abstracts
biomed/1471-2253-2-4.txt:        and unpublished updates of other published Cochrane reviews
biomed/1471-2288-2-10.txt:          studies that they are sponsoring. The Cochrane Library
biomed/1471-2431-3-4.txt:          is in line with a recent Cochrane report in which the
biomed/1471-2458-2-6.txt:        within the Cochrane Collaboration, now tabulates 516 case
biomed/1471-2458-2-6.txt:        papers listed in the Cochrane review to clarify the
biomed/1471-2458-2-6.txt:          Cochrane review note some co-medication taken along with
biomed/1471-2458-2-6.txt:          case reports in the Cochrane review. [ 26 ] Bem et al
biomed/1472-6882-3-1.txt:          Cochrane Collaboration [ 45 ] and others [ 46 47 ] .
biomed/1472-6882-3-1.txt:          FirstSearch, Cochrane, Osteopathic Database, and Index to
biomed/1472-6882-3-1.txt:        ] statements as well as the Cochrane criteria. In addition
biomed/1472-6920-1-3.txt:            Cochrane Library ®, and Best Evidence ®. MEDLINE was
biomed/1472-6920-1-3.txt:        encourage searching of the Cochrane Library. We
biomed/1472-6920-1-3.txt:        because the Cochrane Library addresses only selected
biomed/1472-6920-1-3.txt:        Cochrane reviews and high quality systematic reviews from
biomed/1472-6920-1-3.txt:        Evidence and the Cochrane Library [ 13 ] , influenced
biomed/1472-6947-1-5.txt:        Cochrane Database of Systematic Reviews [ 7 ] , and the
biomed/cc2190.txt:          meta-analysis software (RevMan 4.1; Cochrane
```

**Example 2**

```
ketan@KINKY MINGW64 ~/Downloads/docsearch-main/technical
$ grep -r "cardiotoxic" biomed/
biomed/1468-6708-3-7.txt:          catecholamine levels are cardiotoxic [ 15 ] . Elevated
biomed/1475-2867-3-3.txt:          as a marker of cardiotoxicity [ 13 ] . The mean percent
biomed/1475-2867-3-3.txt:          cardiotoxicity, the remaining portion of the heart that
biomed/1475-2867-3-3.txt:        Evidence for cardiotoxicity, as observed in this study,
biomed/1475-2867-3-3.txt:        of cardiotoxicity but are not definitive.
biomed/1475-2867-3-3.txt:        cardiotoxic effects of DOX chemotherapy [ 26 ] whereas
biomed/1475-2867-3-3.txt:        cardiotoxicity [ 27 28 ] . Shinoyawa et al. [ 28 ] suggest
```

Source [here](https://linuxize.com/post/how-to-use-grep-command-to-search-files-in-linux/)

## **grep -i [Word] [File]**
**What does it do?**

It performs a case-insensitive search for a pattern within a specified file or set of files.

**How is it useful?**

It can be used when we need to search for a pattern, but we are not sure if the pattern is in uppercase or lowercase letters.

**Example 1**

```
ketan@KINKY MINGW64 ~/Downloads/docsearch-main/technical
$ grep -i "flights" 911report/chapter-1.txt
INSIDE THE FOUR FLIGHTS
Boarding the Flights
    The 19 men were aboard four transcontinental flights.
    The hijackers attacked sometime between 8:42 and 8:46. They used knives (as reported by two passengers and a flight attendant), Mace (reported by one passenger), and the threat of a bomb (reported by the same passenger). They stabbed members of the flight crew (reported by a flight attendant and one passenger). Both pilots had been killed (reported by one flight attendant). The eyewitness accounts came from calls made from the rear of the plane, from passengers originally seated further forward in the cabin, a sign that passengers and perhaps crew had been moved to the back of the aircraft. Given similarities to American 11 in hijacker seating and in eyewitness reports of tactics and weapons, as well as the contact between the presumed team leaders, Atta and Shehhi, we believe the tactics were similar on both flights.
    American 77 pushed back from its gate at 8:09 and took off at 8:20. At 8:46, the flight reached its assigned cruising altitude of 35,000 feet. Cabin service would have begun. At 8:51, American 77 transmitted its last routine radio communication. The hijacking began between 8:51 and 8:54. As on American 11 and United 175, the hijackers used knives (reported by one passenger) and moved all the passengers (and possibly crew) to the rear of the aircraft (reported by one flight attendant and one passenger). Unlike the earlier flights, the Flight 77 hijackers were reported by a passenger to have box cutters. Finally, a passenger reported that an announcement had been made by the "pilot" that the plane had been hijacked. Neither of the firsthand accounts mentioned any stabbings or the threat or use of either a bomb or Mace, though both witnesses began the flight in the first-class cabin.
    At 9:00, American Airlines Executive Vice President Gerard Arpey learned that communications had been lost with American 77. This was now the second American aircraft in trouble. He ordered all American Airlines flights in the Northeast that had not taken off to remain on the ground. Shortly before 9:10, suspecting that American 77 had been hijacked, American headquarters concluded that the second aircraft to hit the World Trade Center might have been Flight 77. After learning that United Airlines was missing a plane, American Airlines headquarters extended the ground stop nationwide.        
    The hijackers had planned to take flights scheduled to depart at 7:45 (American 11), 8:00 (United 175 and United 93), and 8:10 (American 77). Three of the flights had actually taken off within 10 to 15 minutes of their planned departure times. United 93 would ordinarily have taken off about 15 minutes after pulling away from the gate. When it left the ground at 8:42, the flight was running more than 25 minutes late.
    The airlines bore responsibility, too. They were facing an escalating number of conflicting and, for the most part, erroneous reports about other flights, as well as a continuing lack of vital information from the FAA about the hijacked flights. We found no evidence, however, that American Airlines sent any cockpit warnings to its aircraft on 9/11. United's first decisive action to notify its airborne aircraft to take defensive action did not come until 9:19, when a United flight dispatcher, Ed Ballinger, took the initiative to begin transmitting warnings to his 16 transcontinental flights: "Beware any cockpit intrusion- Two a/c [aircraft] hit World Trade Center." One of the flights that received the warning was United 93. Because Ballinger was still responsible for his other flights as well as Flight 175, his warning message was not transmitted to Flight 93 until 9:23.
    The terrorists who hijacked three other commercial flights on 9/11 operated in five-man teams. They initiated their cockpit takeover within 30 minutes of takeoff. On Flight 93, however, the takeover took place 46 minutes after takeoff and there were only four hijackers. The operative likely intended to round out the team for this flight, Mohamed al Kahtani, had been refused entry by a suspicious immigration inspector at Florida's Orlando International Airport in August.
    At least two callers from the flight reported that the hijackers knew that passengers were making calls but did not seem to care. It is quite possible Jarrah knew of the success of the assault on the World Trade Center. He could have learned of this from messages being sent by United Airlines to the cockpits of its transcontinental flights, including Flight 93, warning of cockpit intrusion and telling of the New York attacks. But even without them, he would certainly have understood that the attacks on the World Trade Center would already have unfolded, given Flight 93's tardy departure from Newark. If Jarrah did know that the passengers were making calls, it might not have occurred to him that they were certain to learn what had happened in New York, thereby defeating his attempts at deception.
    Passengers on three flights reported the hijackers' claim of having a bomb. The FBI told us they found no trace of explosives at the crash sites. One of the passengers who mentioned a bomb expressed his belief that it was not real. Lacking any evidence that the hijackers attempted to smuggle such illegal items past the security screening checkpoints, we believe the bombs were probably fake.     
    Another commercial aircraft in the vicinity then radioed in with "reports over the radio of a commuter plane hitting the World Trade Center." The controller spent the next several minutes handing off the other flights on his scope to other controllers and moving aircraft out of the way of the unidentified aircraft (believed to be United 175) as it moved southwest and then turned northeast toward New York City.
    The controller responded, seconds later: "Somebody call Cleveland?"This was followed by a second radio transmission, with sounds of screaming. The Cleveland Center controllers began to try to identify the possible source of the transmissions, and noticed that United 93 had descended some 700 feet. The controller attempted again to raise United 93 several times, with no response. At 9:30, the controller began to poll the other flights on his frequency to determine if they had heard the screaming; several said they had.
```

**Example 2**

```
ketan@KINKY MINGW64 ~/Downloads/docsearch-main/technical
$ grep -i "war" 911report/chapter-10.txt
            WARTIME
            Rice said President Bush began the meeting with the words, "We're at war," and that Director of Central Intelligence George Tenet said
                they were not aware of the issue at all until it surfaced much later in the media.
                operations center made sure that the FBI was aware of the flights of Saudi nationals
            PLANNING FOR WAR
                advisers, a group he would later call his "war council."33This group usually
                meeting, he stressed that the United States was at war with a new and different kind
                agreed to every U.S. request for support in the war on terrorism. The next day, the
                avoid malice toward any people, religion, or culture.
                15-16, as President Bush convened his war council at Camp David.
                proposed inserting CIA teams into Afghanistan to work with Afghan warlords who would
                assign tasks for the first wave of the war against terrorism. It starts today."
                Threat to the United States." The directive would now extend to a global war on
                striking Iraq during "this round" of the war on terrorism.
                for the war on terrorism specified three priority targets for initial action: al
            President Bush told Bob Woodward that the decision not to invade Iraq was made at the
                the war on terrorism.
            Shelton told us the administration reviewed all the Pentagon's war plans and
            Having issued directives to guide his administration's preparations for war, on
            President Bush argued that the new war went beyond Bin Ladin." Our war on terror
                in a cave complex called Tora Bora. In March 2002, the largest engagement of the war
```

Source [here](https://linuxize.com/post/how-to-use-grep-command-to-search-files-in-linux/)







