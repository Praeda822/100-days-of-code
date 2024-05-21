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

### Day 6: Saturday, 11th May, 2024

#####

**Today's Progress**: Worked on some MORE DOM manipulation and event propagation in JavaScript!

**Thoughts:** DOM propagation is...hard? I mean, I understand the whole bubbling concept and how I can propagate events upwards (or downwards). Worked a lot with _mouseenter_, and _mouseover_, even though _mouseenter_ doesn't bubble it's still extremely to use in the event where I **don't** want to, inevitably, apply a callback function to ~1000 elements in the DOM with a _forEach()_ loop.

Regarding DOM Traversal/Manipulation, I also learned about the _closest_ method, which is SOOOOO helpful when working with this event delegeation sort of stuff and I've been using it when I need to find a particular parent of an element that matches a specified selector, i.e:

_h1.closest('.header').style.background = 'var(--gradient-secondary)';_

_h1.closest('h1').style.background = 'var(--gradient-primary)';_

The aforementioned code allows me to manipulate specific elements on the absolute fly, _dynamically_ but **WITHOUT** having to muck about with CSS/SCSS and/or make everything on my webpage static & boring, which honestly is pretty cool. A nice change from using _querySelector()_ all the time, which apparently sucks for code efficiency. The more you know!

**Link to work:** [Advanced DOM & Event Manipulation](https://github.com/Praeda822/Javascript-Notes/tree/master/13%20Advanced%20DOM%20and%20Events)

### Day 7: Sunday, 12th May, 2024

#####

**Today's Progress**: Took a break from my coursework today and got stuck into some (easy) Leetcode!

**Thoughts:** I'm not all that used to doing Leetcode questions, but they're pretty useful for getting my brain to wake up, especially when I start early in the mornings or I feel like a dickhead, for whatever reason, and I think I did pretty well, all things considered. I got the sum function right, I got the string reveral correct too, I even managed to write a function that took a string as an argument and then returned the number of vowels in that string.

Cracked on since I was super-stoked I could understand what was being asked of me, and I wrote a function that took an array of strings and then returned a new array with all the strings capitalized (_notice the pattern with strings here lol_), and then I (_just_) managed to scrape my way through creating a function that takes an array of numbers and returns a new array with all the numbers doubled (_from the original array_).

Then..I got up to the last 3 questions and really started to fumble the ball, consequently burning myself out for the day, but in my defence I did spend a solid 10hrs doing Leetcode & reading documentation. Like I said on X (_formerly known as Twitter lmao_): I can only getter better from here! (_right..?_)

**Link to work:** [Leetcode!](https://github.com/Praeda822/Javascript-Notes/tree/master/13%20Advanced%20DOM%20and%20Events/leetcode.js)

### Day 8: Monday, 13th May, 2024

#####

**Today's Progress**: Back into the coursework today, starting off with building some dynamically tabbed components, I learned about the **Guard Clause** (_sounds way cooler than it is lol_) as well as a new way to utilise the _return_ function in regards to error-checking & validation. I also learned about passing arguments to event handlers in order to create cool, dynamic animations and a unique UX.

**Thoughts:** The guard clause part of today really reminded me of the ternary operators section of the course I did, in that I can use implied logic to achieve the goals I want to (_sorta like process of elimination_). The passing arguments to event handlers part of the course really cooked my chops, epsecially with how much abstraction was involved.. It did get a little bit information overload, but I pushed through, and managed to learn about some dynamic new ways to manage active tabs (_that aren't shitty little event listeners with 20+ lines of SCSS/CSS to make it work_).

The two biggest takeways from today, however, were learning a proper (_and efficient_) way to handle Sticky Navigations, but it was a bit of a mental grind, as I tackled that section towards the very end of the day when I was already exhausted.. That said, though, the _Intersection Observer API_ is pretty rad, and it's very interesting to see the sorts of things I can do with it, like dynamically calculating the height of the viewport rectangle (_const navHeight = nav.getBoundingClientRect().height;_), in addition to revealing elements on scroll AND lazy-loading images dynamically for website efficiency:

    const revealSection = function (entries, observer) {
        const [entry] = entries;
        if (entry.isIntersecting) return;
        entry.target.classList.remove('section--hidden');
        observer.unobserve(entry.target);
    };

    const sectionObserver = new IntersectionObserver(revealSection, {
        root: null,
        rootMargin: '0px',
        threshold: 0.15,
    });

    allSections.forEach(function (element) {
        sectionObserver.observe(element);
        section1.classList.add('section--hidden');
    });

The lazy loading images one really got my head in a spin, but... I'll do some revision first thing in the morning tomorrow and rip back into it! Tomorrow's going to be a big one building dynamic slider components (_I've done it with SCSS using transform: translate and :focus_) so it should be...interesting (_:<_).

**Link to work:** [Image Lazy-Loading, Reveal-On-Scroll, & Sticky Nav!](https://github.com/Praeda822/Javascript-Notes/tree/master/13%20Advanced%20DOM%20and%20Events/script.js)

### Day 9: Tuesday, 14th May, 2024

#####

**Today's Progress**: Today was rad as: I managed to not only follow along the tutorial in building the slider component, but I also managed to **RE-BUILD** it myself!! _AND_ then I managed to re-factor it, cleaned up a lot of my forEach loops and because I've been doing so much of, like, write out my code the first time how I think it works, then I edit it and reiterate on it so it makes sense, THEN I shorten it down.

**Thoughts:** Oh my goodness, it's crazy to think it was what..less than 2 weeks ago and I couldn't even figure out how in the blue moons a forEach loop would work, nor how I should use one lol. It's all just organising how you want the data to interact and then sort of tidying up the code (_housekeeping_) by wrapping (_encapsulating_) my code blocks in their own specific functions, with an init function wrapper.. It's almost too good to be true.

Then, I threw myself in the deep-end and jumped into _Constructor functions_, but..kind of just followed a tutorial on it and I still don't know why or what the fuck the .this is all about lol. I'm probably just being impatient again..

**Link to work:**[Dynamic, Reusable, Modular Slider](https://github.com/Praeda822/Javascript-Notes/blob/master/13%20Advanced%20DOM%20and%20Events/script.js)

**Link to work:** [Dynamic, Reusable, Modular Slider - Constructor](https://github.com/Praeda822/Javascript-Notes/blob/master/13%20Advanced%20DOM%20and%20Events/ModularSlider.js)

### Day 10: Wednesday, 15th May, 2024

#####

**Today's Progress**: Got stuck into the (_easy_) Leetcode grind again, today, because I'm a professional procrastinator!

**Thoughts:** So...I sort of burnt myself out yesterday doing that constructor function and then trying to figure out how it works.. I should have just stopped whilst I was on a high with the slider, _lol_.

I ripped into some Leetcode, though | I'm surprisingly getting a lot better at breaking down problems I see and converting them into blocks of code: The first filtering array one was pretty simple, as was repeating the string.

I also got to practice some input validation & error checking using my short circuiting skills from _AGES_ ago. It really is just repetition after all, huh..

**Link to work:**[EZ Leetcode Grindin', pt. 2: Electric Boogaloo](https://github.com/Praeda822/Javascript-Notes/blob/master/13%20Advanced%20DOM%20and%20Events/leetcode.js)

### Day 11: Thursday, 16th May, 2024

#####

**Today's Progress**: Another day of _semi_-procastination.... Made a shitty rock-paper-scissors game out of, _mostly_, Javascript by manipulating the DOM.

**Thoughts:** I'm a serial procastinator, so I sat down today and whipped together a very shitty rock, paper, scissors game. How original, right?

That said it _was_ good practice with dom manipulation, but I need to be more consistent with how I select things.. I don't know why I keep alternating between using ids and query selectors. I just need more practice making dodgy apps, I guess.

I implemented some of the concepts I'm most familiar with, like my random number generator(s), disgusting if/else blocks, and the contribution to a net carbon increase of Global Warming in the namespace. I did some refactoring, though, mainly with arrow functions and readability (_the first iteratrion was gross, lmao_). Good day, but, I enjoyed doing that little project.

**Link to work:**[Rock, Paper, Scissors](https://github.com/Praeda822/RockPaperScissors)

### Day 12: Friday, 17th May, 2024

#####

**Today's Progress**: Today...I stopped putting off the data science theory lectures and ripped into the next section: **Object Oriented Programming with Javascript**!

**Thoughts:** Man, **fuck** Javascript, honestly. Look, I get it, it's _not_ an object oriented language in the traditional sense, and using it like one is the literal difinition of three steps forwards, two steps back, but I digress..

I _really_ learned about **abstraction**, **encapsulation**, **inheitance**, and **polymorphism** today, and I _really_ wish I hadn't (_OK, I am, but it was **a LOT** to take in at once_). I got into **Prototypal Inheritance**, **Constructor Functions** (_and their implementation_), and had a bit of a sticky beak at **ES6 classes** and started to do some work on creating **Prototypes** before I felt completely burnt out with information overload. _Brilliant_.

**Link to work:**[Object Oriented Programming in Javascript](https://github.com/Praeda822/Javascript-Notes/tree/master/14%20OOP%20with%20Javascript)

### Days 13 & 14: Saturday & Sunday, 18th-19th May, 2024

#####

**Today's Progress**: I've spent the last two days actively avoiding the data science theory and decided I'd do some more practice with DOM Manipulation, and taking the logic from my rock paper scissors project, I made..what was _originally_ a text adventure, like a _Choose-Your-Own-Adventure_ sorta'schtick.

I spent **way** too long writing up a story for it all, just to inevitably scrap it because I'm an idiot and didn't think it would be a wise choice to at least _number_ the story slides so I didn't get confused, lol. _lmao_, even.

**Thoughts:** I burned myself out so hard trying to drill the theory into my head that I'm back to being a procastinating POS!

Well, not _really_. But this project was genuinely a lot of fun, because in the end I've been able to dynamically update what's on my screen based upon multiple-choice user-provided input, and it works dynamically, because I learned in the data science section (_that I'm not a fan of_), that since Objects in Javascrript are just reference copies to **Prototypes**, I can just call my method on the raw **object** _protype_ itself, and slap a cheeky _forEach_ loop & a cb function on it, too:

    // Clear previous choices
    function displayScene(sceneKey) {
        const scene = scenes[sceneKey];
        storyElement.innerHTML = scene.text;

    // Clear previous choices
        choicesElement.innerHTML = '';

    // Display the choices
        Object.keys(scene.options).forEach(choiceText => {
            const button = document.createElement('button');
            button.textContent = choiceText;
            button.classList.add('game--button');
            button.onclick = () => {
                if (scene.action) scene.action();
                currentScene = scene.options[choiceText];
                displayScene(currentScene);
            };
            choicesElement.appendChild(button);
            });
        }

    // Start the game by displaying the initial scene
        displayScene(currentScene);

How **good** is destructuring, _right_? Of course, I ended up mutating the entire project into a more...quiz kind of thing, and where I really struggled was in just geting the sum total results from counting up the votes to display at the end.. For some reason this has been a MASSIVE ballache, but I'll sleep on it and tackle it with a fresh pair of eyes tomorrow..

**Link to work:**[My shitty text game](https://github.com/Praeda822/PK_TextAdventure)

### Day 15: Monday, 20th May, 2024

#####

**Today's Progress**: I **finished** the quiz app!!!!! Oh my god it was the _dumbest_ problem ever that got me:

_ALL_ I needed to do was to check if the results scene was present, and if it was, to call the function responsible for picking the class.. I really got some good practice refactoring my code again, especially regarding making sure that my functions do **_ONE THING SPECIFICALLY_**. Thing I'm most proud of is that 've still managed to keep the logic that displays the choices just...working, and all from using a simple _forEach()_ loop.

I'm still _not_ making it live, though: though the quiz logic _works_, and I'm (_somewhat_) confidently manipulating the DOM (_and the google search engine - people on StackOverflow are rude dogs, lmao_), but it still needs way more work with the CSS. I might make a full-blown SASS project out of this one, I'm not sure yet. Still feels **incredible** to have it in a working state!!

**Thoughts:** I feel so stupid. But at the same time, like, I genuinely feel like I'm starting to _get_ it? Idk, it's weird, I can understand what's going on and I'm (_somehow_) keeping it all working, refactoring as I go and trying to shortern code where possible without making it look _too_ jank.. But I still kind of feel like if I stop paying attention, or stop coding for even a day or two, that it will all just _fall out of my head_. Despite that stressor, though, things are going _well_ after 2 weeks of code. Again, I wonder if _anyone_ reads these..

**Link to work:**[PKs Text Adventure](https://github.com/Praeda822/PK_TextAdventure)

### Day 16: Tuesday, 21st May, 2024

#####

**Today's Progress**:

**Thoughts:**

**Link to work:**[Object Oriented Programming in Javascript](https://github.com/Praeda822/Javascript-Notes/tree/master/14%20OOP%20with%20Javascript)
