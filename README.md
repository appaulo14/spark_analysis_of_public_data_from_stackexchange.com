# Finding the Most Common Topics on askubuntu.com
## Abstract
~~The abstract is used by readers to quickly review the overall content of the paper.  Journals typically place strict word limits on abstracts, such as 200 words, making them a challenge to write.  The abstract should provide a complete synopsis of the research paper and should introduce the topic and the specific research question, provide a statement regarding methodology and should provide a general statement about the results and the findings.  Because it is really a summary of the entire research paper, it is often written last.~~

Analyzed public data on askubuntu and found most common topics to identify what areas Ubuntu developers might benefit from focusing on. Tags were the most useful. Word counting the body text was less useful. Word counting the titles was TBD. 

## Introduction
Big Data consists of largs amounts of unstructured or semi-structed data that can be analyzed to derrive new insights that can not easily be found by manually search the data. For example, one could parse gigabytes of server log files to find common causes of errors or slowdowns on a cluster of servers. Another example would be analyzing tweets from Twitter to determine public sentiment about a product. A third example would be analyzing customer buying behavior to better deliver targeted advertising. 

This article focuses on analyzing the questions on askubuntu.com to find the most common topics asked about in order to better understand what areas of Ubuntu may need more attention for bug fixing and also what features might be good to add in future releases o Ubuntu.

I'm in no way affiliated with Ubuntu itself. This analysis is for demonstration purposes only. 

## Methods
The data was obtained from the [Stack Exchange Data Dump on archive.org](https://archive.org/details/stackexchange), after which it was extracted out of its 7z achived and the XML files were uploaded to HDFS storage on Microsoft Azure. From there, the Spark code was developed in Python in an HD Insights cluster following this [Azure HD Insights/Spark guide](https://docs.microsoft.com/en-us/azure/hdinsight/hdinsight-apache-spark-jupyter-spark-sql). The tags (Tags.xml), question titles(Posts.xml), and body of the questions(Posts.xml) were analyzed. 

Spark Version: 2.0
Exact command run: spark-submit find_top_tags_for_askubuntu.com.py
TODO: Upload/mention results files. 

Used Jypter notebooks for prototyping. 

## Results

### Top 100 words in body of question, filtering out generic words such as prepositions and conjunctions
TODO: Filter out a few more things. 
[(715309, u'ubuntu'), (713784, u'0'), (477814, u'1'), (415354, u'can'), (329433, u'install'), (304088, u'2'), (286386, u'sudo'), (279546, u'file'), (224475, u'3'), (220617, u'use'), (211330, u'04'), (205929, u'apt'), (197517, u'gt'), (192560, u'linux'), (189999, u'using'), (184321, u'all'), (179910, u'how'), (179026, u'boot'), (172296, u'windows'), (172064, u'installed'), (171396, u'10'), (167766, u'4'), (167122, u'system'), (149351, u'run'), (143196, u'command'), (140953, u'like'), (140175, u'error'), (136753, u'up'), (136714, u'etc'), (130072, u'after'), (129652, u'usr'), (128874, u'dev'), (128485, u'one'), (127692, u'files'), (127519, u'00'), (127499, u'lt'), (123257, u'problem'), (122438, u'm'), (122246, u'version'), (121726, u'some'), (118332, u'usb'), (118213, u'org'), (117208, u'need'), (114679, u'5'), (113204, u'root'), (112221, u'only'), (111619, u'12'), (111264, u'server'), (110969, u'8'), (109867, u'now'), (108946, u'desktop'), (108507, u'work'), (105769, u'package'), (104991, u'device'), (104714, u'new'), (104588, u'try'), (104410, u'set'), (104174, u'user'), (104016, u'help'), (102698, u'see'), (100452, u'kernel'), (100275, u'14'), (99981, u'd'), (99919, u'update'), (99853, u'home'), (99721, u'make'), (97950, u'packages'), (97840, u'7'), (97763, u'terminal'), (94853, u'alt'), (94706, u'other'), (94612, u'open'), (94242, u'partition'), (93830, u'running'), (93421, u'amp'), (90387, u'default'), (89638, u'following'), (89064, u'tried'), (88720, u'x'), (88216, u'image'), (87776, u'time'), (87748, u'name'), (87025, u'grub'), (86468, u'don'), (86136, u'type'), (85953, u'line'), (84885, u'same'), (84839, u'out'), (83676, u'way'), (83399, u'stack'), (82593, u'6'), (82455, u'found'), (82452, u'directory'), (82372, u'imgur'), (82153, u'src'), (81892, u'add'), (80967, u'bin'), (80715, u'gnome'), (80338, u'software'), (80023, u'screen')]

TODO: Mention total tags 
### Top 25 Tags
Below are the top 25 tags out of 3,022 total tags.  
1. (u'14.04', 21148)  
2. (u'12.04', 17412)  
3. (u'boot', 13098)  
4. (u'command-line', 12294)  
5. (u'networking', 12101)  
6. (u'16.04', 11278)
7. (u'dual-boot', 10458
8. (u'drivers', 9723)
9. (u'unity', 9122)
10. (u'wireless', 9018)
11. (u'server', 8852)
12. (u'apt', 8589)
13. (u'grub2', 7755)
14. (u'partitioning', 7474)
15. (u'installation', 7221)
16. (u'nvidia', 6498)
17. (u'gnome', 5818)
18. (u'system-installation', 5651)
19. (u'upgrade', 5507)
20. (u'bash', 5470)
21. (u'usb', 5404)
22. (u'package-management', 5356)
23. (u'11.10', 5125)
24. (u'software-installation', 5054)
25. (u'sound', 4961)

### Top 100 words in Title
TODO

## Discussion/Conclusion
TODO: Add 1st place mentions, etc. 
Tags were the most useful. The most common questions seemed to be about Ubuntu LTS releases (12.04, 14.04, 16.04), with all three recent LTS releases being in the top 6 tags. A lot of questions are related to booting (boot (3rd place),grub2, uefi). This might be due to the wide variety of hardware Ubuntu but can't say for sure. A lot about windows too (dual-boot,windows,windows-7,windows-8). Networking issues common (5th place for networking), 10th place for wireless, and XYZ place of network-manager. Drivers in 8th place. Graphis: ATI/NVidia, multiple monitors,  compiz. Sounds issues (sound, pulseaudio).  Various others here and there. 

~~This section should be a discussion of the results and the implications on the field, as well as other fields. The hypothesis should be answered and validated by the interpretation of the results.  This section should also discuss how the results relate to previous research mentioned in the literature review, any cautions about the findings, and potential for future research.~~

Future research might try using a natural language parsing library such as [NLTK](http://www.nltk.org/) to better identify topics asked about and also better identify what type of questions are asked for each topics. 

Maybe also looks at scores in the future. 

Maybe focus on less than top 100. 
