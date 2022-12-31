# Codecademy Hurricane Analysis Project

## Project Overview

The Hurricane Analysis project explored data related to Category 5 Hurricanes. This project was the conclusion to the section on Python Dictionaries, and involved writing functions to organize and manipulate the hurricane data in different dictionaries.

## Methodology

Throughout this project I used for loops to iterate through the data and create lists and dictionaries, or find specific data points.

### Challenges

Working with dictionaries was a new challenge for me. I'm used to working in SQL databases and R data frames and vectors, and I had to adjust to how data is stored, indexed, and manipulated in Python dictionaries.

When I ran into problems with my code (like the output of a function being incorrect or not what I expected), I broke the functions down into parts or simplified the functions so I could see what the output of those parts of the functions was. This helped me better visualize what the code was doing and what data I had to work with and helped me find the root causes of issues in my code.

An additional challenge I encountered (that was a bit self-imposed) was accidentally mixing up syntax and variable usage between languages. After I completed all the questions I compared my code to the provided solution code, and found some notable differences between my results and the results provided in the solution code.

After some investigation and some assistance from the Codecademy Discord community, I found the issue was that I was initializing and incrementing a count variable like you would in C, rather than letting the for loop in my code increment the variable automatically.

This was most obvious in question 4. The incorrect code I wrote was:

    def damaged_areas_dictionary(hurricane_dictionary, years):
        i = 0
        damaged_areas_dictionary = {}
        affected_areas = []
        affected_areas_unique = []
        for i in range(0, len(hurricane_dictionary)):
            hurricane = hurricane_dictionary[years[i]]
            hurricane_areas = hurricane["Areas Affected"]
            affected_areas += hurricane_areas
            i += 1
        for area in affected_areas:
            if area in damaged_areas_dictionary.keys():
                damaged_areas_dictionary[area] += 1
            else:
                damaged_areas_dictionary.update({area: 1})
        return damaged_areas_dictionary

You can see I initialized i to 0 and incremented it at the end of the first for loop. This led to i increasing by two every time the for loop was executed, causing the function to skip over data in the input dictionary, resulting in missing data in the output dictionary.

After discovering that issue, I reviewed all the code I'd written for the project and found I'd made the same mistake on other questions. I rewrote the code for all the questions I'd made that mistake on, but left the incorrect code commented out on question 4.

## Conclusion

I learned a lot through this project. Not just about writing functions and using dictionaries, but also about troubleshooting my code and how to narrow down where a function is broken or incorrect.

I also found that in rewriting my code after discovering the issue in Question 4, I was able to write code that was more efficient. I think that was partially because rewriting the code was giving me additional practice, and partially because I already had a pretty good idea of everything the function needed and was able to pull in more knowledge and methods of answering the question than when I was first trying to figure out how the function would need to work.

While the issue with my count variables was difficult to find and time-consuming to solve, it was definitely a worthwhile lesson to learn and I expect it will help me down the line.
