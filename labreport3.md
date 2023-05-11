# The `grep` Command

The `grep` command searches a particular file for a pattern of characters inputted. The command will display all of the lines that match this inputted pattern. `grep` stands for "global search for regular expression and print out". There are many ways to use the `grep` command. A few ways to use the command are given in this page. This information was found on [this](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) website. 

## `grep -o` command

The `grep -o` command prints out only the parts of the text file that match the inputted pattern line by line. It does not print out the entire matching line as the grep command does, but rather just the matching parts of the matching line. Information about this command was found on [this](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) website. 
```
$ grep -o "NORAD Mission and Structure" ./technical/911report/chapter-1.txt
$ **NORAD Mission and Structure**
```
In the example above, the command looks for "NORAD Mission and Structure" and returns just the part of the text that matches this given pattern. Since there is just one line that matches, "NORAD Mission and Structure" is printed out just once. This command will be useful in this case since now we know how many times important words show up.
```
$ grep -o "Florida" ./technical/911report/chapter-1.txt
$ **Florida**
$ **Florida**
$ **Florida**
$ **Florida**
$ **Florida**
```
In this second example, I used the `grep -o` command to look for "FLorida." Since this pattern was mentioned five times, "Florida" printed five times line afer line, unlike the previous example that printed the pattern once. This command will print out the pattern the number of times it shows up in the file. This command is useful because we can look for common patterns in the file and see how many times it shows up.

## `grep -h` command

The `grep -h` command displays the lines that match the pattern inputted, but it does not show the name of the file associated with the matched lines displayed. Information about this command was found on [this](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) website.
```
$ grep -h "Lipid" ./technical/biomed/1468-6703-3-10.txt
$        The Antihypertensive and **Lipid** Lowering Treatment to
```
In this example, I used the `grep -h` command to look up "Lipid" in the file. As a result, it returned the entire line that contained this pattern. Since there is only one line that contains "Lipid," only one line shows up. This is very useful because if we are looking for an uncommon phrase, we will easily be able to look it up by using the line it is in and then looking for it in the file.
```
$ grep -h "treatment" ./technical/biomed/1468-6703-3-10.txt
$        older, between those randomized to **treatment** initiated with
        a diuretic (chlorthalidone) and **treatment** initiated with
        recommendation to discontinue the doxazosin **treatment** arm
        compare these features between the two **treatment**
          distributed across the four **treatment** groups, reported as
          differences among **treatment** groups.
          **treatment**s for HF [ 6 7 8 9 ] , was compared between
          **treatment** groups were presented for baseline
          characteristics of the **treatment** and HF outcome groups
          chlorthalidone **treatment** groups, stratified for HF
          pre-trial antihypertensive **treatment** durations. None of
          Table 2presents post-event pharmacologic **treatment** of
          participants with HF and antihypertensive **treatment** of
          **treatment** groups, a diuretic, ACE-inhibitor or
          P = 0.83) between the two **treatment**
          **treatment** group who had been previously hospitalized for
          significantly differ in the two **treatment** groups (RR
        documentation were similar in the two **treatment** groups [ 2
        **treatment** groups confirmed the consistency of HF event
        beta-blockers, all recognized **treatment**s for HF, were
        the two **treatment** groups.
        chlorthalidone **treatment** groups showed a rather high 20%
        and chlorthalidone **treatment** groups represented a desirable
```
In this example, I looked for "treatment" in this file, which is a more common word. As a result there were several lines that were displayed with the word "treatment" bolded. This is useful in this case because when we want to find a specific occurrence of a common word, we can use this command to see which line we need to go to in order to find a specific piece of information.

## `grep -v` command

The `grep -v` command does the opposite to the commands described above. This command instead prints out all of the lines that do not match the inputted pattern. Information about this command was found on [this](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) website. 
```
$ grep -v "a" ./technical/biomed/1468-6708-3-10.txt
$
  
    
      
        
        lipid-lowering component is designed to determine if
        (RR 2.04; 95% CI, 1.79-2.32; 
        groups.
      
      
        Methods
        
          Study Design
          the drug groups?
          groups?
        
        
          The ALLHAT definition of HF, used previously in the
        
        
        
        
          collected up to July, 1999, the time of the review.
        
        
        
        
        
      
      
        Results
        
          The blinded review by the Endpoints Subcommittee of 50
        
        
          P < .05.
          13% of those without; 
          those with HF vs. 23-25% of those without; 
          with HF: 47-48% in those with HF, 35-36% in those without
          ( 
          P < .001).
        
        
        
        
        
        
          CI, 0.67-1.38, 
          1.03, 95% CI 0.90-1.15, 
          P = 0.56) [ 2 ] .
        
      
      
        Discussion
        HF reports reviewed by the ALLHAT Endpoints Subcommittee
        size.
      
      
        Competing Interests
        (AZ,BMS,F,M,P,PHU,SY,SE,SV,T), JTW (A,B,BMS,F,KM, M,N,P),
        report no competing interests.
      
      
        higher dose, it is permitted.
      
    
  

```
In this example, I used the `grep -v` command to look at all the lines that did not contain "a." This example used a letter rather than a phrase in order to show that the pattern can be however long or short. This command is useful if we want to avoid certain information to condense a large text.
```
$ grep -v "." ./technical/biomed/1468-6703-3-10.txt
$
```
In this example, I used this command to look up lines that did not contain a period. The command in this case returned nothing since every line in the text contains a period. This command is particularly useful in this case if we want to see how common certain phrases are and to see if there are any lines without a certain pattern.

## `grep -c` command

Use the `grep -c` command in order to see the number of lines that match the inputted pattern. This command displays the number of lines that match the pattern. Information about this command was found on [this](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) website. 
```
$ grep -c "North America" ./technical/plos/journal.pbio.0020001.txt
$ 6
```
This example shows using `grep -c` to see the specific count for how many times a specific word shows up in a file. This could be more useful than the `grep -o` command, especially when using common words so that you do not have to count how many times a word or pattern appears.
```
$ grep -c "sjdwidhiwjd" ./technical/biomed/1468-6703-3-10.txt
$ 0
```
This example shows what would happen when a pattern is not in a file. The `grep -c` command would return 0 on phrases that do not exist in the file. This is useful in this case to see if a file is about a certain topic. If it is not, then key words probably will not appear in the file.
