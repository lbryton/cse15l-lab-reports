#  Lab 5 Week 10 Report:
- The purpose of this lab is to compare the differences in results between the outputs of our group's MarkdownParse and the MarkdownParse provided for Week 9.

Lab Links:
- [Index](https://lbryton.github.io/cse15l-lab-reports/index.html)
1. [Lab Report 1](https://lbryton.github.io/cse15l-lab-reports/LabReport1/lab-report-1-week-2.html)
2. [Lab Report 2](https://lbryton.github.io/cse15l-lab-reports/LabReport2/lab-report-2-week-4.html)
3. [Lab Report 3](https://lbryton.github.io/cse15l-lab-reports/LabReport3/lab-report-3-week-6.html)
4. [Lab Report 4](https://lbryton.github.io/cse15l-lab-reports/LabReport4/lab-report-4-week-8.html)

Pre Lab Notes:

1. Lab Report [here](https://ucsd-cse15l-w22.github.io/week/week10/#lab-report-5)
2. Links:
- Link to my markdown-parse [repository](https://github.com/lbryton/markdown-parse)
- Link to provided markdown-parse [repository](https://github.com/ucsd-cse15l-w22/markdown-parse)

## Part 1: Difference 1
- Method used to find difference: Used the `diff` command to find the differences between the outputs of each MarkdownParse
> When running `diff` between the results of each MarkdownParse, one of the differences was when the the provided code outputed `[url]` while my group's code outputed `[]`:
>![Image](Part1A.png)
> 
>Looking into the output files for both, I realize that the test file `194.md` was the file that caused the discrepancy (Provided code output on the left image, group's code provided on the right)
>
>![Image](Part1Provided.png)![Image](Part1Group.png)
>:
>

## Part 2: Testing Snippet 1 on Reviewed Group's MarkdownParse 
- Did it pass: No
> Reason: There is no implementation in our group's code to determine if a possible link is an actual link if there are backticks. 
>![Image](Part2A.png)

## Part 3: Testing Snippet 2 on Our Group's MarkdownParse 
- Did it pass: No
> Reason: 
>![Image](Part3A.png)
> Method of solution: I do not think that making a small (<10 line) code change will make my group's program work for snippet 2. Just like the backticks in snippet 1, there will also be many different cases for nested and escaped brackets and parentheses. If I were to implement these features, I would create one method to check for escaped brackets, a recursive methods to find nested brackets and another recursive method to find nested parentheses.

## Part 4: Testing Snippet 2 on Reviewed Group's MarkdownParse 
- Did it pass: No
> Reason: 
>![Image](Part4A.png)

## Part 5: Testing Snippet 3 on Our Group's MarkdownParse 
- Did it pass: No
> Reason: 
>![Image](Part5A.png)
> Method of solution: I think that it would be possible that making a small (<10 line) code change will make my group's program work for snippet 3. First I would replace the `containsSpace` variable and replace it with code that would trim off spaces before and after the link. For example: `"( abc )"` as a link to `[abc]` as a return for the `getLinks` method. The next thing I would do is create a method to determine if there are consecutive line spaces (two or more `\n`) within the link or link title and remove them if they exist to allow the code to get the links properly.

## Part 6: Testing Snippet 3 on Reviewed Group's MarkdownParse 
- Did it pass: No
> Reason: 
>![Image](Part6A.png)