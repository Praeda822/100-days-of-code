# 100 Days Of Code - Log

### Day 1: Monday, 6th May, 2024

#####

**Today's Progress**: Got stuck into my Javascript course again, focused on working with Integers and learning Discrete Math (modulo/remainder operator)

**Thoughts:** I pushed through the boring parts and it's actually payed off big time with my learning process. Man, section 9, the Data Structures and Javascript Behind The Scenes, callstacks, heaps, Primitives; none of it really made sense at the time when I watched it months ago, but now, having watched it again recently-and having pushed forward with the coursework despite feeling like a dickhead-I can finally contextualise it, and abstract it in my head which helps SO much with both writing code in general, as well as re-factoring my code to clean it up.

He's got us working on this Bank app at the moment, it's 11:54pm and I just got home from a 2.5hr gym session consisting of BOTH chest & shoulders so I am _rooted_. I'll link all the work.....when I upload it tomorrow after getting my beauty sleep. And maybe an update of what's been going on since I last sat down to really code (_christmas, btw.._) because MAN life's been hectic. I wonder if people really read these things anyway, lol.

**Link to work:** [Bankist App](https://github.com/Praeda822/Javascript-Notes/tree/master/12%20Numbers%2C%20Dates%2C%20Times/starter)

### Day 2: Tuesday, 7th May, 2024

#####

**Today's Progress**: Today I did some more work on my Banking app, working specifically with more dates, times, and integers, as well as how to both manipulate the data, and transform said data into whatever I need it to be. Also went back into my Javascript Data Structures & Theory lectures.

**Thoughts:** Today was mainly spent just mucking around with the new Date() method because I'm an idiot and sometimes don't understand on the first go through..or fifth. I worked on primarily getting the transaction list to be functional by means of having the transactions reflect an automatically calculated time/date (In the Commonwealth format: _DAY, MONTH, YEAR_, sorrynotsorry Americans) and to also have those same dates/times/etc reflect upon other accounts' transaction history, like say if I wanted to take a loan, I can now hit the button and not only have that transaction reflect instantly, but also have it reflect, again, on other accounts, but this was only using template literals which is a bit...messy. I'll refactor it again tomorrow, and see how I go; my brain is fried again from doing this shit for hours straight.

**Link to work:** [Bankist App](https://github.com/Praeda822/Javascript-Notes/tree/master/12%20Numbers%2C%20Dates%2C%20Times/starter)

### Day 3: Wednesday, 8th May, 2024

#####

**Today's Progress**: More work on the banking app today... Spent way too long mucking around with the Intl API, and worked on getting more dates to reflect on the app dynamically

**Thoughts:** So.. I somehow managed to break the trnasfer money part of my app..Still not sure how though, lol. Everything else works: requesting a loan, closing an account, changing users etc. Also managed to completely break the Sort button at the bottom, which no longer sorts and just deletes the entire transaction list which isn't ideal.. but I reckon it's going to be a, wait for it, TOMORROW PROBLEM because it's 11:45pm and I am, again, rooted, having slogged through more of my course content as soon as I got off work.

I'm pleased with how it's all going, however, I just wish I had a bit more motivation to smash out way more code like I was able to before I busted my hand, but typing for hours is starting to hurt (which is kinda weird).. But I digress, tomorrow I'm going to finally finish off this secttion and then I'm off the discrete mathematics & itenegers for a bit, and on to more advanced DOM manipulation and then OOP with Javascript (god help me lol).

**Link to work:** [Bankist App](https://github.com/Praeda822/Javascript-Notes/tree/master/12%20Numbers%2C%20Dates%2C%20Times/starter)

### Day 4: Thursday, 9th May, 2024

#####

**Today's Progress**: Final bits of the Banking app numbers section finished today, AND I fixed both the sort button bug and the transfer money bug; what a relief!!

**Thoughts:** OK, so I'm the biggest dickhead ever: I spent a good hour or two trying to work out why my sort button was bugging out and causing all of my transactions to disappear from the transactions movements list, so I stepped through it with the debugger (thinking to myself, "_fuck, how am I going to fix this.._") and came to the realisation that......it was just a typo. LOL. Literally:

_let sorted = false;_
_btnSort.addEventListener('click', function (e) {_
_e.preventDefault();_
_// Original bug that broke the sort button:_
_// displayMovements(currentAccount.movements, !sorted);_
_displayMovements(currentAccount, !sorted);_
_sorted = !sorted;_
_});_

That's the now working code above. What broke it was that I was trying to pass ONLY the movements array to my function, but my function was expecting the _ENTIRE OBJECT_, **inclusive** of the movements array. I literally just had to remove _.movements_ to redefine my object as it is: just the object.

I also managed to have almost the exact same bug (_also a typo.._) with my transfer button, since originally I had typed it as **movementDates**:

_receiverAcc.movementsDates.push(new Date().toISOString());_

And voila, just like that, everything works again just like magic. What an absolute ballache it was trying to figure out what were just two silly little typos.. Life's hard when you're an idiot, eh.

**Link to work:** [Bankist App](https://github.com/Praeda822/Javascript-Notes/tree/master/12%20Numbers%2C%20Dates%2C%20Times/starter)

### Day 5: Friday, 10th May, 2024

#####

**Today's Progress**: Worked on DOM manipulations and event handling in JavaScript! Implemented modal interactions, manipulated styles, and attributes dynamically, and played with advanced event handling concepts like event bubbling and capturing. Learned about the power of _.addEventListener_ and the nuances of event propagation

**Thoughts:** I legit had no idea you could accomplish so much with _.addEventListener_.. I feel a bit silly thinking about all the previous code I've written and how it looks like hot garbage because I would apply my event listeners directly to static objects containing my elements instead of doing it dynamically like I learned today. Really got stuck into the nitty gritty of how Javascript works behind the scenes today, too; what a _HEADACHE_.

But I'd be lying if I said that learning the core concepts of JavaScript's engine and runtime, understanding execution contexts, the call stack, and memory management as well as the importance of scoping, and the distinctions between primitive and reference types in regards to memory management hasn't made a world of difference in understanding just how my code works. Now I can abstract whats happening a bit more clearly in my head. It has felt like I have had an epiphany by discovering something new every day this week, now my head's swimming with ideas of things I could build over the weekend...

**Link to work:** [Advanced DOM & Event Manipulation](https://github.com/Praeda822/Javascript-Notes/tree/master/13%20Advanced%20DOM%20and%20Events)
