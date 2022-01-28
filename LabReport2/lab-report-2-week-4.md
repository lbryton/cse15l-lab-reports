# Week 4 Lab 2 Report:
- This lab report is to describe 3 bug changes in MarkdownParse.java to remove incorrect ouputs

Lab Links:
- [Index](https://lbryton.github.io/cse15l-lab-reports/index.html)
1. [Lab Report 1](https://lbryton.github.io/cse15l-lab-reports/LabReport1/lab-report-1-week-2.html)

Pre Lab Notes:

1. Forked code with bug fixes [here](https://github.com/lbryton/markdown-parse)
2. Original code by Joe Politz [here](https://github.com/ucsd-cse15l-w22/markdown-parse)

## Error 1: Incorrect Checks for Indexes
> The first error my lab group decided to fix was when the values for  `nextOpenBracket`, `nextCloseBracket`, and `openParen` was `-1` (or the indexes of `[`,`]`, or `(`), the code would sometimes neglect these index indicators. This was because the code would only check for `closeParen` to end the while loop. One symptom of this error is that the code would run in an infinite loop. When running this [test file](https://github.com/lbryton/markdown-parse/blob/main/testfile1.md), an example of this type of failure-inducing input, the results in the image below occur:
![Image](Part1A.png)
>The command line actions above depicted the needs to manually terminate the program to end the infinite loop.
To fix this error, I allowed the program to check if any of the values for `nextOpenBracket`, `nextCloseBracket`, and `openParen` and `closeParen` were `-1` to break out of the while loop:
>![Image](Part1diff.png)


## 2. Error 2: Distance Between Closed Bracket and Open Parentheses
> The next error my lab group decided to fix was the difference in index values from `nextCloseBracket`, and `openParen`. For a correctly formated link, the open parentheses comes right after the closed bracket. However, the original code will pick up the closed bracket and open parentheses in this failure-inducing input from this [test file](https://github.com/lbryton/markdown-parse/blob/main/testfile2.md). The contents for this file are show below:
>```
>For set we use brackets ([]) instead of >paratheses (())
>```
> Because there is no link in the test file, the program should return a blank `ArrayList`. However, the original code returns a `(` as shown below:
>![Image](Part2A.png)
>To fix this issue, I made these changes to the original code:
>![Image](Part2diff.png)

## 3. Error 3: Images Are Counted As Links
> Another error my lab group decided to fix to add another parameters to define a link. For markdown, the method to create links and images are quite similar. The method to create links are `[link text](website link)`, while the method to create an image is `![Image name](Link to image)`.  However, the original program does not differentiate between a link and an image when returning the links. As a result, this [test file](https://github.com/lbryton/markdown-parse/blob/main/testfile3.md) is a failure-inducing input and produced the response below instead of a blank `ArrayList`.
>![Test](Part3A.png)
>To fix this issue, my group and I checked if there is an exclamation mark (`!`)before the open bracket (`[`) to prevent images from being counted as lists. The changes to fix this code are show below:
>![Image](Part2diff.png)