---
layout: essay
type: essay
title: "How curiosity killed the developer"
# All dates must be YYYY-MM-DD format!
date: 2025-01-30
published: true
labels:
  - Questions
  - Answers
  - StackOverflow

# The goal of this exercise is not to “prove” that asking questions the smart way is always better (although it would be quite interesting to design an empirical study using StackOverflow to actually gather data on whether “smart” questions do indeed, on average, lead to more effective and efficient answers). Instead, the goal of this exercise is to help you form a deeper understanding of what constitutes “smart” and “not smart” questions so that you are more likely to ask smart ones in the future.

# Write a technical essay that discusses why smart questions are important for smart software engineers, how the chosen questions fulfill (or not) the precepts for smart questions, how the responses reflect the smartness (or lack thereof), and the insights you gained as a result of this experience.
---

<img width="100%" src="../img/essays-img/questions.png">

## Curiosity: a tragic cause of death

Throughout the life cycle of various programs and projects, both experienced and newbie programmers alike eventually encounter issues that they simply do not know the answer to. This is where the distinction between experienced and newbie is exposed; experienced programmers embark on a troubleshooting process that involves due diligence and asking smart questions, whilst newbies programmers may feel inclined to immediately ask for help.

Though understandable, this newbie instinct to _ask questions first, think later_ is unfortunately what leads to a prevalent (but very real) cause of death for most projects and programs: **death by curiosity.**

## An autopsy

To elaborate, death by curiosity occurs when programmers, developers, or hackers impatiently attempt to find answers without performing a troubleshooting process. Such a scenario leads to a rushed, incomprehensible query that is less likely to be responded to. At best, this leads to receiving a helpful answer with a side of shaming or online ridicule. At worst, development is either delayed or outright canceled due to no responses whatsoever, hence a "death" of a project.

Consider the following example of [death by curiosity from StackOverflow](https://stackoverflow.com/questions/79401719/getting-data-map-is-not-a-function), a forum site consisting of user-generated queries and responses. 

```
Q: Getting data.map is not a function

I'm getting error todos.map is not a function, only that line gives error if I remove the div of the mapping then the code works fine. All the other functions and components works fine, then why is this not working.

Please someone explain this, todos is an array then why the mapping is not working here.
```

Preceding the paragraphs is plain-text code from the user program.

This example of death by curiosity can be better described as a case study of **how to not properly ask questions**. For a better understanding, I will review the post from top to bottom.

- The title of the question is vague, despite using the 'javascript' tag. The question title, **'Getting data.map is not a function'**,provides no insight into the problem being encountered and poses more confusion for readers, requiring more effort to be put into understanding the problem than discussing a solution.

- Code is the first item posted; this practice can be overwhelming and confusing due to the lack of context. If I were an expert attempting to answer this question, I would not understand much at this point aside from "getting data.map is not a function".

Therefore, this question clearly demonstrates that the user did not make sincere efforts to resolve their issue diligently and simply sought a quick fix. 



Stack Overflow, a question and answer site for programmers, is a great resource for anyone who may have issues with code or who may simply want to learn new or different methods of doing something. There I found examples of good questions and bad questions, which could probably be improved.

In the following example, we examine the components of a decent question. In this case, the asker is trying to figure out a way to get the date of the previous month in Python.

```
Q: python date of the previous month

I am trying to get the date of the previous month with python. Here is what i've tried:

str( time.strftime('%Y') ) + str( int(time.strftime('%m'))-1 )

However, this way is bad for 2 reasons: First it returns 20122 for the February of 2012 (instead of 201202) 
and secondly it will return 0 instead of 12 on January.

I have solved this trouble in bash with:

echo $(date -d"3 month ago" "+%G%m%d")

I think that if bash has a built-in way for this purpose, then python, much more equipped, should provide something 
better than forcing writing one's own script to achieve this goal. Of course i could do something like:

if int(time.strftime('%m')) == 1:
    return '12'
else:
    if int(time.strftime('%m')) < 10:
        return '0'+str(time.strftime('%m')-1)
    else:
        return str(time.strftime('%m') -1)
        
I have not tested this code and i don't want to use it anyway (unless I can't find any other way:/)

Thanks for your help!
```

While the heading of his question could be better, it does convey what he’s trying to figure out. Usually something as brief as “python date of previous month” is what other users would enter in as search terms on Google, making it easily found. Another good thing about the question is that it’s not just a question. The asker shows what he or she has done and that he or she has put in some effort to answer the question. And while it may not be as important as the question itself, the asker shows courtesy, which does increase the chance of getting an answer.

```
A: datetime and the datetime.timedelta classes are your friend.

1. find today
2. use that to find the first day of this month.
3. use timedelta to backup a single day, to the last day of the previous month.
4. print the YYYYMM string you're looking for.

Like this:

 >>> import datetime
 >>> today = datetime.date.today()
 >>> first = datetime.date(day=1, month=today.month, year=today.year)
 >>> lastMonth = first - datetime.timedelta(days=1)
 >>> print lastMonth.strftime("%Y%m")
 201202
 >>>

```
 
The asker received six possible answers, and he or she was successful in inciting discussion from multiple users. The answers themselves were clear and were devoid of the rumored sarcasm and hostility of “hackers.” Since I myself have referenced this page and found it useful, I can confidently say that it is a good question.

## Surviving curiosity as a developer

While there are decent questions that benefit everyone, there are those one can ask to create an entirely different effect. In the following example, a user asks how he would, in short, create a desktop application with Facebook.

```
Q: Facebook Desktop Notifier

I am a beginner programmer that have never used anything other than what's included in a language.

I am trying to create a desktop application that notifies me anytime I get an update onfacebook. 
How should go about doing this? Thanks in advance.

edit Sorry I was not clear. Is there any way to make a DESKTOP application with facebook?
```

A simple “yes” would have answered the question, but we know that’s not the sort of answer he or she is looking for. Fortunately, someone kindly responded with a link to Facebook’s developer website. The asker should have done more research on his or her potential project. Then further down the road, he or she could have asked more specific and detailed questions that wouldn’t require a thousand-paged response for a sufficient answer.

## Conclusion

When we rely on others’ generosity and expertise to provide answers to our questions, it should hold that the question we ask should be one that leads to efficient and effective help that not only benefits us, but also the people we ask and others who might ask the same question in the future. Thus, if you have a question… make it a smart one! Asking questions may not always get you the best answer, but asking them in a way that will make others want to answer them will increase the success of finding a good solution and make it a positive experience on all sides.
