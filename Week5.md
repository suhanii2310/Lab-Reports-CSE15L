# Week 5 Lab Report

## Researching Commands

## Command 1 (grep -l)

- This command line option of grep is used to search for a specific pattern in a set of files and diplays only the names of files that match the search patter.
- We can explain this using the following examples
- In example 1, we search for "Taj Mahal" and it displays all the files that conatin this string.
- Similarly in example 2, when we search for the string "Pisa", the command searches for all the files containing the string "Pisa" and prints all the files.

Example 1
```
suhanisrivastava@Suhanis-MacBook-Air-2 skill-demo1-data % grep -r -l "Taj Mahal" written_2
written_2/travel_guides/berlitz1/HistoryIndia.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz1/WhatToJamaica.txt

```

Example 2

```
suhanisrivastava@Suhanis-MacBook-Air-2 skill-demo1-data % grep -r -l "Pisa" written_2
written_2/non-fiction/OUP/Kauffman/ch8.txt
written_2/travel_guides/berlitz1/HistoryItaly.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz1/IntroItaly.txt
written_2/travel_guides/berlitz1/HistoryIbiza.txt
written_2/travel_guides/berlitz1/WhatToItaly.txt
written_2/travel_guides/berlitz2/Budapest-WhereoGo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt

```
(I found out about this through chatGPT)


## Command 2 (grep -i)

- This command line option of grep is used to conduct a case-insensitive search. With `-i` the search pattern is not affected by the case of the letters.
- To understand this better we can use the following examples.
- In example 1, we searched for the word "sweet". Even though in the search pattern we entered "sWeEtS" it still matches all the lines containing this word. It doesnt matter in what case we type the word.
- Similarly, in example 2 we search for the word "Eiffel Tower". We entered the search pattern as "eiFfeL toWeR" the command searches for all the files containing this string irrespective of the case.
- In both the examples we use the `-l` command such that it prints only the file name and not the whole string.

Example 1 

```
suhanisrivastava@Suhanis-MacBook-Air-2 skill-demo1-data % grep -r -i -l "sWeEtS" written_2
written_2/non-fiction/OUP/Castro/chO.txt
written_2/travel_guides/berlitz1/WhatToIbiza.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt

```

Example 2

```
suhanisrivastava@Suhanis-MacBook-Air-2 skill-demo1-data % grep -r -i -l "eiFfeL toWeR" written_2
written_2/travel_guides/berlitz1/HistoryFrance.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhereToEgypt.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/IntroLasVegas.txt
written_2/travel_guides/berlitz2/California-WhereToGo.txt
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
```
(I found out about this through chatGPT)


## Command 3 (grep -x)
- This command line option is used to match only complete lines that exactly match the specific pattern. This option allows you to search for a string that must appear as a whole line, rather than as a substring within a line.
- We can understand this with the following examples. 
- In example 1, we search for a specific line. here we search for the line "In 1947 Edinburgh hosted its first International Festival." and it displays the file "WhatToEdinburgh".
- Similarly in the second example we search for the line "It is no place for the .... myth attaches to India.". It prints the file "IntroIndia".
- In both the examples we use the `-l` command such that it prints only the file name and not the whole string.

Example 1

```
suhanisrivastava@Suhanis-MacBook-Air-2 skill-demo1-data % grep -r -x -l  "In 1947 Edinburgh hosted its first International Festival." written_2
suhanisrivastava@Suhanis-MacBook-Air-2 skill-demo1-data % grep -r -x -l  "The Festival Fringe was born at the same time as the
        official festival and acts as a sometimes irreverent, loose collection
        of extra performances held in the city." written_2
written_2/travel_guides/berlitz1/WhatToEdinburgh.txt

```
Example 2

```
suhanisrivastava@Suhanis-MacBook-Air-2 skill-demo1-data % grep -r -x -l  "It is no place for the faint-hearted.
        India is exhilarating, exhausting, and infuriating — a land where,
        you’ll find, the practicalities of daily life overlay the mysteries
        that popular myth attaches to India." written_2
written_2/travel_guides/berlitz1/IntroIndia.txt

```

(I found out about this through chatGPT)


## Command 4 (grep -c)

- This command line option is used to count the number of lines in a file that match the specified pattern, rather than printing the actual matching lines.
- We can understand this using the following examples.
- In the first example, we search for the word "vacation". This command searches for the word "vacation" and counts the number of lines in each file that contain this word. It then returns the name of the files along with the number of lines that contain the specific word.
- Similarly, in example 2, the command counts the lines in files that contain the word "history".

Example 1

```
suhanisrivastava@Suhanis-MacBook-Air-2 skill-demo1-data % grep -r -c "vacation" written_
2
written_2/non-fiction/OUP/Berk/ch2.txt:3
written_2/non-fiction/OUP/Berk/ch1.txt:0
written_2/non-fiction/OUP/Berk/CH4.txt:0
written_2/non-fiction/OUP/Berk/ch7.txt:0
written_2/non-fiction/OUP/Abernathy/ch2.txt:0
written_2/non-fiction/OUP/Abernathy/ch3.txt:0
written_2/non-fiction/OUP/Abernathy/ch1.txt:0
written_2/non-fiction/OUP/Abernathy/ch7.txt:0
written_2/non-fiction/OUP/Abernathy/ch6.txt:0
.
.
.
.
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt:1
written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Cuba-History.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:3
written_2/travel_guides/berlitz2/Bahamas-History.txt:2
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt:1

```

Example 2

```
suhanisrivastava@Suhanis-MacBook-Air-2 skill-demo1-data % grep -r -c "history" written_2

written_2/non-fiction/OUP/Berk/ch2.txt:3
written_2/non-fiction/OUP/Berk/ch1.txt:2
written_2/non-fiction/OUP/Berk/CH4.txt:0
written_2/non-fiction/OUP/Berk/ch7.txt:0
written_2/non-fiction/OUP/Abernathy/ch2.txt:1
written_2/non-fiction/OUP/Abernathy/ch3.txt:0
written_2/non-fiction/OUP/Abernathy/ch1.txt:3
written_2/non-fiction/OUP/Abernathy/ch7.txt:0
written_2/non-fiction/OUP/Abernathy/ch6.txt:2
written_2/non-fiction/OUP/Abernathy/ch8.txt:0
written_2/non-fiction/OUP/Abernathy/ch9.txt:0
written_2/non-fiction/OUP/Abernathy/ch15.txt:1
written_2/non-fiction/OUP/Abernathy/ch14.txt:0
written_2/non-fiction/OUP/Rybczynski/ch2.txt:0
.
.//shortened output
.
.
written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt:3
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Cuba-History.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:2
written_2/travel_guides/berlitz2/Bahamas-History.txt:2
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt:7

```

(I found out about this through chatGPT)

# The Source

I used chatGPT to find out about the above command line options.
I searched for "grep command line options" and it returned a few of the options.


![F0FE3675-27DE-4191-8DDA-3F4DD91662C7](https://user-images.githubusercontent.com/122580828/218439211-2cc29adb-3ee2-49e9-84de-684eafb5db01.jpeg)
![F4F7B7B2-5184-4623-A3AC-7EC4F84E7CD4](https://user-images.githubusercontent.com/122580828/218439225-ffedc9f7-544f-448c-a9df-d62ef49934c9.jpeg)
