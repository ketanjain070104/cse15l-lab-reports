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
