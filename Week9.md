# Week 9 Lab Report

## Researching Commands

## Command 1 (find -name)

- This command line option of find is used when we know the name of the file and want to know its location.
- We can explain this using the following examples
- In example 1, we search for a file named `HistoryIndia.txt`. The output shows that the file was found in the directory `./written_2/travel_guides/berlitz1/`.
- Similarly in example 2, we search for a file named `HistoryItaly.txt`. The output shows that the file was found in the directory `./written_2/travel_guides/berlitz1/`.

Example 1
```
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % find . -name HistoryIndia.txt
./written_2/travel_guides/berlitz1/HistoryIndia.txt
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch %
```

Example 2

```
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % find . -name HistoryItaly.txt  
./written_2/travel_guides/berlitz1/HistoryItaly.txt
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch %

```
(I found out about this through tecmint.com)


## Command 2 (find -iname)

- This command line option of find is used to conduct a case-insensitive search. With `-iname` the search pattern is not affected by the case of the letters.
- To understand this better we can use the following examples.
- In example 1, we search for a file named `HiStoRyHawAiI.txt`. The output shows that the file was found in the directory `./written_2/travel_guid`. It doesnt matter in what case we type the filename.
- Similarly, in example 2 we search for the file `Athens-Intro.txt`. We entered the search pattern as "AtHenS-INTro.txt" the command searches for all the files containing this string irrespective of the case. The fiel was found in the directory `./written_2/travel_guides/berlitz2/Athens-Intro.txt`.

Example 1 

```
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % find . -iname HiStoRyHawAiI.txt 
./written_2/travel_guides/berlitz1/HistoryHawaii.txt
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % 

```

Example 2

```
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % find . -iname AtHenS-INTro.txt 
./written_2/travel_guides/berlitz2/Athens-Intro.txt
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % 
```
(I found out about this through linuxhandbook)


## Command 3 (find -type f -name <filename> -exec rm -f {} \;)
- The `-type` option is used to specify the type of file to search for. The `-name` option is used to specify the name of the file to search for. The `-exec` option is used to execute a command `-rm -f` to remove the file.
- We can understand these with the following examples. 
- In example 1, the command searches for the file "Cancun-WhereToGo.txt" and then uses -exec to execute the -rm -f command to delete the file. We check if the file was deleted or not by using -name command to search for this file. We observe that it doesn't return anything which means the file was deleted.
- Similarly in the second example, the command searches for the file "Cuba-History.txt" and then uses -exec to execute the -rm -f command to delete the file. We check if the file was deleted or not by using -name command to search for this file. We see that it doesn't return anything which means the file was deleted.

Example 1

```
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % find . -type f -name "Cancun-WhereToGo.txt" -exec rm -f {} \;
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % find . -name Cancun-WhereToGo.txt         
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % 
```
Example 2

```
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % find . -type f -name "Cuba-History.txt" -exec rm -f {} \;
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % find . -name Cuba-History.txt                            
suhanisrivastava@Suhanis-MacBook-Air-2 docsearch % 


```

(I found out about this through tecmint.com)


## Command 4 (find . -mtime)

- This command line option is used to find all the files that were modified within the last few days(number entered).
- We can understand this using the following examples.
- In the first example, the command `-mtime -2` returns all the files that were modified in the last two days. This returns `./travel_guides/berlitz2`
- Similarly in the second example the command `-mtime -40` returns all the files that were modified in the last forty days.

Example 1

```
suhanisrivastava@Suhanis-MacBook-Air-2 written_2 % find . -mtime -2
./travel_guides/berlitz2

```

Example 2

```
suhanisrivastava@Suhanis-MacBook-Air-2 written_2 % find . -mtime -40
.
./non-fiction
./non-fiction/OUP
./non-fiction/OUP/Berk
./non-fiction/OUP/Berk/ch2.txt
./non-fiction/OUP/Berk/ch1.txt
./non-fiction/OUP/Berk/CH4.txt
./non-fiction/OUP/Berk/ch7.txt
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Abernathy/ch2.txt
.
.//shortened output
.
.
./travel_guides/berlitz2/Budapest-History.txt
./travel_guides/berlitz2/China-WhatToDo.txt
./travel_guides/berlitz2/Athens-WhatToDo.txt
./travel_guides/berlitz2/Nepal-WhatToDo.txt
./travel_guides/berlitz2/Bermuda-WhereToGo.txt
./travel_guides/berlitz2/Paris-WhatToDo.txt
./travel_guides/berlitz2/Vallarta-WhereToGo.txt
./travel_guides/berlitz2/Beijing-WhatToDo.txt

```

(I found out about this through linuxhandbook)

# The Source
  
I used google to find out about the below sites to find command line options.
I searched for "find command line options" and clicked on the following sites.
  
## Source 1
- I used this site to look for the comands `-name` and `-type f -name <filename> -exec rm -f {} \;`.
  
https://www.tecmint.com/35-practical-examples-of-linux-find-command/ 
  

![9F75C527-A583-4DC6-A522-86C53A11BCA8](https://user-images.githubusercontent.com/122580828/224828606-cbe99d8c-dffb-4c2d-be40-d7e132be6c61.jpeg)
![3251FB4F-8AC6-4857-B280-E9BACF0A4142](https://user-images.githubusercontent.com/122580828/224828634-19a4f0e5-35e0-448d-9afb-f761c262d7e4.jpeg)

## Source 2
- I used this site to look for the comands `-iname` and `-mtime`.
  
https://linuxhandbook.com/find-command-examples/ 
  
![E565653B-3FA4-4108-BCBA-CB3B446F1EC6](https://user-images.githubusercontent.com/122580828/224829081-8738f710-f627-48ad-9534-d684a9c281b4.jpeg)
![8FA80DA0-0252-435F-9B2F-AC0C5F2DF93E](https://user-images.githubusercontent.com/122580828/224829112-f554520b-73b5-4756-a7be-abeaf5659b06.jpeg)

 
