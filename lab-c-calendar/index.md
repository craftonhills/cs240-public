# C Programming: Calendar

Introduction: Prompt the user for a day (1 – 31), month (1 – 12), and year (1753 – 9999) and print out the day
corresponding to that date—that is, Sunday, Monday, Tuesday, etc. After printing the day of the week, your
program should exit.
The `*text*` below represents user input. You may assume correct user input.

##Example: 
    Enter day: *1*
    Enter month: *1*
    Enter year: *2003*
    January 1, 2003 is a Wednesday.

##Specifics: 

There is an easy way to find the day of the week given a date known as Zeller’s Rule. The rule is
as follows: 

    f = {day + [((13*month)-1)/5] + D + [D/4] + [C/4] - 2*C} mod 7.

Anything within [] should be rounded down (to the smaller integer). Here, month is an integer from 1 to 12, with
Mar being 1, Apr being 2, . . . , Jan being 11, and Feb being 12. Jan and Feb count as the 11th and 12th months of
the previous year, respectively. D is the last 2 digits of the year and C is the first 2 digits of the year. For January
28, 2034, for example, D is 33, C is 20, and month is 11. Sunday corresponds to f = 0, Monday is f = 1, etc. If f is
negative, you must add 7.

See [http://mathforum.org/dr.math/faq/faq.calendar.html](http://mathforum.org/dr.math/faq/faq.calendar.html) for more information.

Test your program with representative test cases. Copy your test results into a text file named RESULTS.txt.  You will submit this text file along with your C program.

##Before Your Start

You will clone your class personal repository onto your local machine:

    $ git clone https://github.com/craftonhills/cs240-flast.git
    Cloning into 'cs240-flast'...

The name of your cs240 personal repository is *cs240-flast*, where 'f' is your first initial and 'last' is your last name.

Put your lab files in your cs240-flast repository since this is where you will submit your lab files.

##Submitting Your Completed Lab

You will submit your lab on your CS240 personal repository on GitHub. 

The submission of your lab should be done by the date and time the it is due.

The criteria for your lab being submitted on time is that your code must be pushed by the date and time. This means that if the instructor were to open up GitHub, they would be able to see your solutions on the GitHub web page.

Just because your code has been commited on your local machine, that doens't mean that it has been submitted; it needs to be on GitHub.

Here are a few guideline steps for a process of submitting your solutions:

In the terminal, nagivate to the directory containing your completed program and test results. 


Look at your current repository status.

    $ git status
Add your solutions (if they aren't already added and commited).

    $ git add my-solutions/
Commit your solutions.

    $ git commit
Enter your commit message and then save and exit.

*This is the most important part: push your solutions to GitHub.*

    $ git push 
   
The last thing that we strongly recommend you do is to go to the craftonhills organization page on GitHub to make sure that I can see your solutions.

Just navigate to your repository and check that your latest commits are on GitHub.

The go and eat some cinnamon rolls; you've finished the lab assignment.
