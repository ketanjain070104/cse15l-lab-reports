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







