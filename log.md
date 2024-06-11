# 100 Days Of Code - Log

### Day 1: Monday, 6th May, 2024

#####

**Today's Progress**: Got stuck into my Javascript course again, focused on working with Integers and learning Discrete Math (modulo/remainder operator)

**Thoughts:** I pushed through the boring parts and it's actually payed off big time with my learning process. Man, section 9, the Data Structures and Javascript Behind The Scenes, callstacks, heaps, Primitives; none of it really made sense at the time when I watched it months ago, but now, having watched it again recently-and having pushed forward with the coursework despite feeling like a dickhead-I can finally contextualise it, and abstract it in my head which helps SO much with both writing code in general, as well as re-factoring my code to clean it up.

He's got us working on this Bank app at the moment, it's 11:54pm and I just got home from a 2.5hr gym session consisting of BOTH chest & shoulders so I am _rooted_. I'll link all the work.....when I upload it tomorrow after getting my beauty sleep. And maybe an update of what's been going on since I last sat down to really code (_christmas, btw.._) because MAN life's been hectic. I wonder if people really read these things anyway, lol.

**Link to work:** [Bankist App](https://github.com/Praeda822/Javascript-Notes/tree/master/12%20Numbers%2C%20Dates%2C%20Times/starter)

### Day 2: Tuesday, 7th May, 2024

#####

**Today's Progress:** Today I did some more work on my Banking app, working specifically with more dates, times, and integers, as well as how to both manipulate the data, and transform said data into whatever I need it to be. Also went back into my Javascript Data Structures & Theory lectures.

**Thoughts:** Today was mainly spent just mucking around with the new Date() method because I'm an idiot and sometimes don't understand on the first go through..or fifth. I worked on primarily getting the transaction list to be functional by means of having the transactions reflect an automatically calculated time/date (In the Commonwealth format: _DAY, MONTH, YEAR_, sorrynotsorry Americans) and to also have those same dates/times/etc reflect upon other accounts' transaction history, like say if I wanted to take a loan, I can now hit the button and not only have that transaction reflect instantly, but also have it reflect, again, on other accounts, but this was only using template literals which is a bit...messy. I'll refactor it again tomorrow, and see how I go; my brain is fried again from doing this shit for hours straight.

**Link to work:** [Bankist App](https://github.com/Praeda822/Javascript-Notes/tree/master/12%20Numbers%2C%20Dates%2C%20Times/starter)

### Day 3: Wednesday, 8th May, 2024

#####

**Today's Progress:** More work on the banking app today... Spent way too long mucking around with the Intl API, and worked on getting more dates to reflect on the app dynamically

**Thoughts:** So.. I somehow managed to break the trnasfer money part of my app..Still not sure how though, lol. Everything else works: requesting a loan, closing an account, changing users etc. Also managed to completely break the Sort button at the bottom, which no longer sorts and just deletes the entire transaction list which isn't ideal.. but I reckon it's going to be a, wait for it, TOMORROW PROBLEM because it's 11:45pm and I am, again, rooted, having slogged through more of my course content as soon as I got off work.

I'm pleased with how it's all going, however, I just wish I had a bit more motivation to smash out way more code like I was able to before I busted my hand, but typing for hours is starting to hurt (which is kinda weird).. But I digress, tomorrow I'm going to finally finish off this secttion and then I'm off the discrete mathematics & itenegers for a bit, and on to more advanced DOM manipulation and then OOP with Javascript (god help me lol).

**Link to work:** [Bankist App](https://github.com/Praeda822/Javascript-Notes/tree/master/12%20Numbers%2C%20Dates%2C%20Times/starter)

### Day 4: Thursday, 9th May, 2024

#####

**Today's Progress:** Final bits of the Banking app numbers section finished today, AND I fixed both the sort button bug and the transfer money bug; what a relief!!

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

**Today's Progress:** Worked on DOM manipulations and event handling in JavaScript! Implemented modal interactions, manipulated styles, and attributes dynamically, and played with advanced event handling concepts like event bubbling and capturing. Learned about the power of _.addEventListener_ and the nuances of event propagation

**Thoughts:** I legit had no idea you could accomplish so much with _.addEventListener_.. I feel a bit silly thinking about all the previous code I've written and how it looks like hot garbage because I would apply my event listeners directly to static objects containing my elements instead of doing it dynamically like I learned today. Really got stuck into the nitty gritty of how Javascript works behind the scenes today, too; what a _HEADACHE_.

But I'd be lying if I said that learning the core concepts of JavaScript's engine and runtime, understanding execution contexts, the call stack, and memory management as well as the importance of scoping, and the distinctions between primitive and reference types in regards to memory management hasn't made a world of difference in understanding just how my code works. Now I can abstract whats happening a bit more clearly in my head. It has felt like I have had an epiphany by discovering something new every day this week, now my head's swimming with ideas of things I could build over the weekend...

**Link to work:** [Advanced DOM & Event Manipulation](https://github.com/Praeda822/Javascript-Notes/tree/master/13%20Advanced%20DOM%20and%20Events)

### Day 6: Saturday, 11th May, 2024

#####

**Today's Progress:** Worked on some MORE DOM manipulation and event propagation in JavaScript!

**Thoughts:** DOM propagation is...hard? I mean, I understand the whole bubbling concept and how I can propagate events upwards (or downwards). Worked a lot with _mouseenter_, and _mouseover_, even though _mouseenter_ doesn't bubble it's still extremely to use in the event where I **don't** want to, inevitably, apply a callback function to ~1000 elements in the DOM with a _forEach()_ loop.

Regarding DOM Traversal/Manipulation, I also learned about the _closest_ method, which is SOOOOO helpful when working with this event delegeation sort of stuff and I've been using it when I need to find a particular parent of an element that matches a specified selector, i.e:

_h1.closest('.header').style.background = 'var(--gradient-secondary)';_

_h1.closest('h1').style.background = 'var(--gradient-primary)';_

The aforementioned code allows me to manipulate specific elements on the absolute fly, _dynamically_ but **WITHOUT** having to muck about with CSS/SCSS and/or make everything on my webpage static & boring, which honestly is pretty cool. A nice change from using _querySelector()_ all the time, which apparently sucks for code efficiency. The more you know!

**Link to work:** [Advanced DOM & Event Manipulation](https://github.com/Praeda822/Javascript-Notes/tree/master/13%20Advanced%20DOM%20and%20Events)

### Day 7: Sunday, 12th May, 2024

#####

**Today's Progress:** Took a break from my coursework today and got stuck into some (easy) Leetcode!

**Thoughts:** I'm not all that used to doing Leetcode questions, but they're pretty useful for getting my brain to wake up, especially when I start early in the mornings or I feel like a dickhead, for whatever reason, and I think I did pretty well, all things considered. I got the sum function right, I got the string reveral correct too, I even managed to write a function that took a string as an argument and then returned the number of vowels in that string.

Cracked on since I was super-stoked I could understand what was being asked of me, and I wrote a function that took an array of strings and then returned a new array with all the strings capitalized (_notice the pattern with strings here lol_), and then I (_just_) managed to scrape my way through creating a function that takes an array of numbers and returns a new array with all the numbers doubled (_from the original array_).

Then..I got up to the last 3 questions and really started to fumble the ball, consequently burning myself out for the day, but in my defence I did spend a solid 10hrs doing Leetcode & reading documentation. Like I said on X (_formerly known as Twitter lmao_): I can only getter better from here! (_right..?_)

**Link to work:** [Leetcode!](https://github.com/Praeda822/Javascript-Notes/tree/master/13%20Advanced%20DOM%20and%20Events/leetcode.js)

### Day 8: Monday, 13th May, 2024

#####

**Today's Progress:** Back into the coursework today, starting off with building some dynamically tabbed components, I learned about the **Guard Clause** (_sounds way cooler than it is lol_) as well as a new way to utilise the _return_ function in regards to error-checking & validation. I also learned about passing arguments to event handlers in order to create cool, dynamic animations and a unique UX.

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

**Today's Progress:** Today was rad as: I managed to not only follow along the tutorial in building the slider component, but I also managed to **RE-BUILD** it myself!! _AND_ then I managed to re-factor it, cleaned up a lot of my forEach loops and because I've been doing so much of, like, write out my code the first time how I think it works, then I edit it and reiterate on it so it makes sense, THEN I shorten it down.

**Thoughts:** Oh my goodness, it's crazy to think it was what..less than 2 weeks ago and I couldn't even figure out how in the blue moons a forEach loop would work, nor how I should use one lol. It's all just organising how you want the data to interact and then sort of tidying up the code (_housekeeping_) by wrapping (_encapsulating_) my code blocks in their own specific functions, with an init function wrapper.. It's almost too good to be true.

Then, I threw myself in the deep-end and jumped into _Constructor functions_, but..kind of just followed a tutorial on it and I still don't know why or what the fuck the .this is all about lol. I'm probably just being impatient again..

**Link to work:**[Dynamic, Reusable, Modular Slider](https://github.com/Praeda822/Javascript-Notes/blob/master/13%20Advanced%20DOM%20and%20Events/script.js)

**Link to work:** [Dynamic, Reusable, Modular Slider - Constructor](https://github.com/Praeda822/Javascript-Notes/blob/master/13%20Advanced%20DOM%20and%20Events/ModularSlider.js)

### Day 10: Wednesday, 15th May, 2024

#####

**Today's Progress:** Got stuck into the (_easy_) Leetcode grind again, today, because I'm a professional procrastinator!

**Thoughts:** So...I sort of burnt myself out yesterday doing that constructor function and then trying to figure out how it works.. I should have just stopped whilst I was on a high with the slider, _lol_.

I ripped into some Leetcode, though | I'm surprisingly getting a lot better at breaking down problems I see and converting them into blocks of code: The first filtering array one was pretty simple, as was repeating the string.

I also got to practice some input validation & error checking using my short circuiting skills from _AGES_ ago. It really is just repetition after all, huh..

**Link to work:**[EZ Leetcode Grindin', pt. 2: Electric Boogaloo](https://github.com/Praeda822/Javascript-Notes/blob/master/13%20Advanced%20DOM%20and%20Events/leetcode.js)

### Day 11: Thursday, 16th May, 2024

#####

**Today's Progress:** Another day of _semi_-procastination.... Made a shitty rock-paper-scissors game out of, _mostly_, Javascript by manipulating the DOM.

**Thoughts:** I'm a serial procastinator, so I sat down today and whipped together a very shitty rock, paper, scissors game. How original, right?

That said it _was_ good practice with dom manipulation, but I need to be more consistent with how I select things.. I don't know why I keep alternating between using ids and query selectors. I just need more practice making dodgy apps, I guess.

I implemented some of the concepts I'm most familiar with, like my random number generator(s), disgusting if/else blocks, and the contribution to a net carbon increase of Global Warming in the namespace. I did some refactoring, though, mainly with arrow functions and readability (_the first iteratrion was gross, lmao_). Good day, but, I enjoyed doing that little project.

**Link to work:**[Rock, Paper, Scissors](https://github.com/Praeda822/RockPaperScissors)

### Day 12: Friday, 17th May, 2024

#####

**Today's Progress:** Today...I stopped putting off the data science theory lectures and ripped into the next section: **Object Oriented Programming with Javascript**!

**Thoughts:** Man, **fuck** Javascript, honestly. Look, I get it, it's _not_ an object oriented language in the traditional sense, and using it like one is the literal difinition of three steps forwards, two steps back, but I digress..

I _really_ learned about **abstraction**, **encapsulation**, **inheitance**, and **polymorphism** today, and I _really_ wish I hadn't (_OK, I am, but it was **a LOT** to take in at once_). I got into **Prototypal Inheritance**, **Constructor Functions** (_and their implementation_), and had a bit of a sticky beak at **ES6 classes** and started to do some work on creating **Prototypes** before I felt completely burnt out with information overload. _Brilliant_.

**Link to work:**[Object Oriented Programming in Javascript](https://github.com/Praeda822/Javascript-Notes/tree/master/14%20OOP%20with%20Javascript)

### Days 13 & 14: Saturday & Sunday, 18th-19th May, 2024

#####

**Today's Progress:** I've spent the last two days actively avoiding the data science theory and decided I'd do some more practice with DOM Manipulation, and taking the logic from my rock paper scissors project, I made..what was _originally_ a text adventure, like a _Choose-Your-Own-Adventure_ sorta'schtick.

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

**Today's Progress:** I **finished** the quiz app!!!!! Oh my god it was the _dumbest_ problem ever that got me:

_ALL_ I needed to do was to check if the results scene was present, and if it was, to call the function responsible for picking the class.. I really got some good practice refactoring my code again, especially regarding making sure that my functions do **_ONE THING SPECIFICALLY_**. Thing I'm most proud of is that 've still managed to keep the logic that displays the choices just...working, and all from using a simple _forEach()_ loop.

I'm still _not_ making it live, though: though the quiz logic _works_, and I'm (_somewhat_) confidently manipulating the DOM (_and the google search engine - people on StackOverflow are rude dogs, lmao_), but it still needs way more work with the CSS. I might make a full-blown SASS project out of this one, I'm not sure yet. Still feels **incredible** to have it in a working state!!

**Thoughts:** I feel so stupid. But at the same time, like, I genuinely feel like I'm starting to _get_ it? Idk, it's weird, I can understand what's going on and I'm (_somehow_) keeping it all working, refactoring as I go and trying to shortern code where possible without making it look _too_ jank.. But I still kind of feel like if I stop paying attention, or stop coding for even a day or two, that it will all just _fall out of my head_. Despite that stressor, though, things are going _well_ after 2 weeks of code. Again, I wonder if _anyone_ reads these..

**Link to work:**[PKs Text Adventure](https://github.com/Praeda822/PK_TextAdventure)

### Day 16: Tuesday, 21st May, 2024

#####

**Today's Progress:** I did a lot of javascript methods practice questions and just kinda..got in the vibe of switching my mindset up in regards to coding.

**Thoughts:** So I was following another course I have, from _Brad Traversy_, and it's just like, a shit load of Javascript algorithms and data science practice questions - like self-imposed homework, man, it's _amazing_.

I've been thinking a lot about just coding in general, and I'm really starting to see how valuable and fun it is when you look at everything like, _how do I solve this problem using the tools I have?_, where your tools are the language you utitilise to solve that problem. I'm finding so much of it is just repetition, literally, just repeatedly exposing myself to problems like _how do I want to move this bit of data_, and abstracting the DOM is so cool when you know wtf is going on, I just genuinely don't know how to describe it.

That said, I _still_ need to crack on with the Data Science & THeory section, starting with my favourite: **Prototypes**. I guess software's gotta' run fast, too..

**Link to work:** [OOP In Javascript](https://github.com/Praeda822/Javascript-Notes/blob/master/14%20OOP%20with%20Javascript/script.js)

### Days 17-23: Wednesday-Tuesday, 22nd May-28th May, 2024

**Week's Progress:** This week I started to get my hands dirty with Object-Oriented Programming (_OOP_) concepts, delving into the four fundamental principles: **Abstraction**, **Encapsulation**, **Inheritance**, and **Polymorphism**. I kicked this off with creating simple constructor functions and classes in JavaScript and classes to create objects that can interact with each other.

But you know what we _really_ got into? **_Prototypal Inheritance_**. I learned about how methods are delegated, got my head around the inheritance chain, learned how it's the **PROTOTYPES** themselves that are the big bosses of the Javascript world. I also got to work with setters & getters, and I spent a lot of time learning how to refactor my code, and by that I mean that I want to try to break up my code into individual pieces that have a unique task to do, and they specifically _only_ do that task, then I essentially call those functions on instantiated objects (_I know, fancy, right?_) to interact with them which has been _wild_.

The Biggest thing I worked on was understanding ES6 classes, how they work, their implementation, as well as _WHY_ I want to be using them instead of just polluting the global namespace with my shit. ES6 classes are just a layer of abstraction over Constructor Functions since they hide a lot of what's going on behind the scenes. But that's why we have both the _extends_ & _super_ keywords! Most annoying part about that was having to remember to initialize my _.this_ keyword.

I got stuck in to both _Public/Private Fields/Instances_, and how to implement (_some pretty fuckin' dodgy_) **encapsulation** within my code structure. And I also got to work with using _Object.create()_, which was a really nice way of creating new objects...only then you have to manually set up the prototypal inheritance chain since it **_only_** makes _EMPTY_ objects. Found myself often being a layer out when setting up my inheritance.

**Thoughts:** OK, so I'm summarising the week's work here because FUCK ME did I do some work.

Understanding the prototypal inheritance wasn't anywhere near as bad as I thought it would be. Except, **_maybe_** when we did _this_ shit:

    // First prototype-chain (the inner scope)
        console.log(patrick.__proto__);
    // Second prototype-chain (the inner scope's outer scope & also my constructor)
        console.log(patrick.__proto__.__proto__);
    // Final prototype-chain (the inner scope's outer scope's outer scope, which is NULL)
        console.log(patrick.__proto__.__proto__.__proto__);

That was beyond fucked the first time. But I persevered, and now it actually does make sense in my head and I'm able to kind of _visualise_ the prototype boxes (_that's how I remember it, anyway_). Most importantly, I undestand that it's the **PROTOTYPES** that have access to all the cool methods, not the objects themselves. Which makes **Prototypes** the _de-facto_ landlords of javascript memory management, and the **Objects**, essentially, renters (_since they're delegated methods from their prototypes & via prototypal inheritance my GOD I'm getting GOOD at this shit_)

I'm also really starting to notice a pattern in how coding is, like, _performed_: everything is just about organising data to be displayed to the user in a simple, easy-to-understand, dynamically formatted way for minimal maintenance and/or oversight.

I did, however, read **_Design Patterns: Elements of Reusable Object-Oriented Software_**, by **_The Gang of Four_** not just once, but _twice_, and I **STILL** don't understand a fuckin' thing going on because it's all written in C++. That said, I _did_ gleam some insight out of the book in regards to OOP and Javascript, as well as how I could (_potentially_) use the patterns within my own code, and they were the 5 design patterns: **Factory**, **Singleton**, **Observer**, **Decorator**, and **Adapter**.

I've also been starting to get suprisingly decent at refactoring my code, too, particularly with the whole shortening to arrow function, break it up into functions that do specific things, **HELPER FUNCTIONS** (_OH MY GOOOOOOD_)

**Link to work:** [OOP In Javascript](https://github.com/Praeda822/Javascript-Notes/blob/master/14%20OOP%20with%20Javascript/script.js)

### Days 23-29: Wednesday-Monday, 28th May - Monday 3rd June, 2024

**Week's Progress:** Gonna be another **BIG** one for the week again. I spent the entire week working on a project that revolved entirely around **_OOP and Javascript_** to really hammer home the _PTSD_ from learning OOP for the first-time through the lens of the Javascript language.

I also got to work with using the Geolocation API to get a users location relative to pulling their GPS data out of an online object. How _fuckin'_ rad is **that**!? We went over the project architecture & structure initially, and yeah, _OK_, it took me 2 whole days to get my head around the fact that a flowchart (_gonna call 'em flowie's from now on_) map makes just **starting** a project SO. MUCH. EASIER. It's just ES6 classes; all the way down (_and up, lol_). I also discovered the beauty of, again, bundling my functionalities together, like having a function for all my _eventHandlers_! The more I code, the more I start to see where and what to refactor, which is _so_ sick.

**Thoughts:** I did struggle a bit with rmembering how destructuring works, but then I literally realised that I do destructuring on wow with how abilities and keybinds work, and then all of a sudden, _LIKE FUCKEN MAGIC_, it made sense to me!! I'm _really_ starting to love using mnemonics for coding, it makes things so much easier to understand.

But it wasn't all hand-holding singing*kumbaya* into the fading sunset, _oh no no no_. I ended up getting so lost in the code after looking at it for so long that I was having a meltdown over the fact that I kept geting a return of _NULL_ in the console **for a DOM elemnet I hadn't even fucking _rendered_ yet**, and then I let my stress and over-tiredness spill over into code so whe I fixed one bug 2 _more_ bugs would appear, in this case those new bugs being my **map markers** simply just _disappearing_ off the _fucking_ map!! Oh wait, it was just me being a professional _dickhead_ again and forgetting to _actually update the map with a marker when a new one is rendered in the form_.

I also spent a solid day refactoring code from my old projects, mainly my Text Adventure (_which still isn't done, only God can judge me_), the dice-rolling number game, and the banking app project. Refactoring literally just means _move all your shit into neat & tidy functions that do exactly the same shit, only specifically, and with the functionality to use them on other instantiated objects as methods_. Man, doing this shit for 10hrs a day minimum maybe wasn't the smartest idea, but at least it's going in..

**Link to work:** [Mapty Workout Project](https://github.com/Praeda822/Javascript-Notes/tree/master/15%20Mapty%20Project)

### Day 30: Tuesday, 4th June, 2024

**Today's Progress:** Today I started learning about AJAX: Aynschronous Javascript and XML. The theory part was great, but then I hit a huge blocker in regards to the actual course content itself:

    const btn = document.querySelector('.btn-country');
    const countriesContainer = document.querySelector('.countries');

    // The OLD SKOOL Way
    // ========================================

    // FINALLY I'll assign this entire functionality to its own respective function
    const getCountryData = function (country) {
    // First I create a new object and call the XMLHttpRequest() function, storing that result in a variable

    const request = new XMLHttpRequest();

    // Next I call the open function on my variable and pass in the 'GET' data-type, followed by a string containing where the AJAX call needs to be made
    // This is also known as the API Endpoint
    request.open('GET', `https://restcountries.com/v3.1/name/${country}`, true); // ensure async is true

    // ADDED: Set a timeout for the request to handle potential timeout issues
    request.timeout = 10000; // Set timeout to 10 seconds

    // And I'll then need to SEND that request off
    request.send();

    // Then I need to register a callback on the request object that listens for the 'load' event
    // So this returns a SHITLOAD of text (in JSON format)
    request.addEventListener('load', function () {
        // And then I need to convert that JSON string into my javascript object
        // Since data is an array containing an object, I can destructure it as well
        if (request.status >= 200 && request.status < 300) {
        // ADDED: Check if the request was      successful
         const [data] = JSON.parse(this.responseText);
        console.log(data);

      // And then I'll create a template literal to create the cool card thing in the HTML
      // Remember I can use + to convert to a number
      const html = `
      <article class="country">
      <img class="country__img" src="${Object.values(data.flags)[0]}" />
      <div class="country__data">
        <h3 class="country__name">${data.name.common}</h3>
        <h4 class="country__region">${data.region}</h4>
        <p class="country__row"><span>👫</span>${(
          +data.population / 25687041
        ).toFixed(1)} people</p>
        <p class="country__row"><span>🗣️</span>${Object.values(
          data.languages
        ).join(', ')}</p>
        <p class="country__row"><span>💰</span>${
          Object.values(data.currencies)[0].name
        }</p>
      </div>
    </article>
    `;
      // And then I'll pretty much just add this to my document by sending it to my countries container
      // Which would be great if I could even FUCKING see it since the API times out every single fucken time
      countriesContainer.insertAdjacentHTML('beforeend', html);
      countriesContainer.style.opacity = 1;
        } else {
        // Handle unsuccessful requests
      console.error('Error:', request.statusText);
        }
    });

    // Error handling for network issues
     request.addEventListener('error', function () {
        console.error('Request failed');
    });

        // Timeout handling
        request.addEventListener('timeout', function    () {
        console.error('Request timed out');
        });
    };

    getCountryData('australia');
    getCountryData('portugal');
    getCountryData('germany');

All that horseshit code you see above you there is _supposed_ to work, and by work, I mean it's meant to render 3 little cards on the screen showing details about those countries, but the course content itself is outdated, and the website responsible for the API can't even be reached.. So Idek wtf to do about it. ChatGPT was able to get it working (_where you can see those Added comments_), but that was only **VERY briefly** as for whatever reason the API just times out over & over again, despite people in the course from _circa ~10 days ago_ stating that they were able to get it all working fine???

**Thoughts:** 30 days of consecutive code!!! And to celebrate my milestone accomplishment I spent probably half of my coding time today just googling shit and feeling like a _right fucking monkey_. But get this, right: I did the full _lazy POS_ shit thing and copy/pasted the code from the QA section, and even _THAT_ times out, **despite** both instructor and student swearing black & blue that it's all _right-and-tight yeah looks good mate_. So I threw my code into ChatGPT, saved, commit, and reviewed the changes on Github and it's using _Object.values()_ to read the properties of the object, when almost **EVERYONE ELSE IN THE ENTIRE GODDAMN QA IS USING ARRAY DESTRUCTURING TO ACCESS THE SAME SHIT**. I even tried passing _Object.create()_ onto the objects themselves and then filling them with the data _from_ that object, _that's_ how fucked up this part of the section was.. Oh, and there's **no** docs for the shit. Nooice.

**Link to work:** [Outdated course content can eat my ass](https://github.com/Praeda822/Javascript-Notes/blob/master/16%20Asynchronous%20Javascript/script.js)

### Days 31-37: Wednesday, 5th June - Tuesday, 11th June 2024

#####

**Week's Progress:** This week I dove into Asynchronous Javascript, in particular Promises and Async/Await. I also spent the week learning about efficiently (and neatly) retrieving data from APIs using these promises by utilising (_and understanding_) asynchronous code

**Thoughts:** **_WOW_**, man, _what a week_.. I tried to procrastinate the theory work as much as I could by starting the week off _diving the fuck into_ learning about Asynchronous code, and conceptualizing how Javascript is like a one-lane highway with a shitload traffic, aka _synchronous code_. But then turns out I can actually run even more code _asynchronously_ in the WebAPI, which is just another part of the _Javascript Runtime Environment_.. I learned about blocking/non-blocking code, _annnnnd_ I **_FINALLY_** learned what a _JSON_ is: it's just a _stupid_ string full of nonsense that represents a javascript object retrieved from an API.

Then I got into learning what was described to me as the "_Old-school way_" of executing asynchronous code: **_AJAX Calls & the XMLHttp Function_**. I had the pleasure of banging my head against the proverbial wall again, as the GeoLocation API we were instructed to use was...outdated (_lmao_), and I'm a stubborn dickhead so I just plowed ahead, using the v3.1 version of that garbage API (_same API that gave me so much grief previously - again, stubborn_) until I just had enough on the Thursday and asked the instructor(s) about what I should do, since I'd run out of ideas and I already felt like a right _POS_ for procrastinating _an entire fucking evening_ by making a really shitty UI mockup for a finance app, a dodgy **Rock-Paper-Scissors** game (_which actually fucking works!_) as well as an even dodgier Connect4 game-which still doesn't work _lol_-trying to avoid even looking at the consistently timing-out geolocation API.

Turns out I'm equally impatient as I am _ridiculously good-looking_, and that not **_ONLY_** did the instructor(s) have their own **working** GeoLocation API just for this project, but that I also had my code in a **WORKING** state and the reason for the constant timeouts was because I have ADSL/2+ internet speeds (_no, seriously, I have ADSL/2+_) **LOL**. _Lmao_, even. Once I got that sorted I _finally_ was excited again to rip back into this section of the course since now I could _literally_ see how my code works instead of just imagining it working.

And then I got stuck into learning about **Promises**. I used to go cross-eyed whenever I saw _Async/Await_ codeblocks: I legimiately thought that they were, and I quote, "_just some react shit i'm not meant to know yet_". Man, how wrong I was _lol_, turns out they're just like check-valves but for Web APIs, and they exist to validate fetched and/or retrievied data (_..not forgetting that **they must always be HANDLED and WRANGLED with error catchers because FUCK you**)_. I learned about **Promisifying**, **Executor (_sick yugioh card btw_) Functions**, as well as the proper syntax for writing them:

    const renderCountry = function (data, className = '') {
    const html = `
      <article class="country ${className}">
      <img class="country__img" src="${Object.values(data.flags)[0]}" />
      <div class="country__data">
        <h3 class="country__name">${data.name}</h3>
        <h4 class="country__region">${data.region}</h4>
        <p class="country__row"><span>👫</span>${
          (+data.population / 1000000).toFixed(1)
          // Our actual pop: 25687041
        }m people</p>
        <p class="country__row"><span>🗣️</span>${data.languages[0].name}</p>
        <p class="country__row"><span>💰</span>${
          Object.values(data.currencies)[0].name
        }</p>
      </div>
    </article>
    `;

    countriesContainer.insertAdjacentHTML('beforeend', html);
    };


    const getJSON = function(url, errorMsg =    'Something went wrong..') {
    return fetch(url).then(response => {
        if (!response.ok) throw new Error(`${errorMsg} (${response.status})`);
        return response.json();
        });
    };

    const getCountryData = function (country) {

        getJSON(``,
        'Country not found'
        )
        .then(data => {
            renderCountry(data[0]);
            const neighbour = data[0].borders ? data[0].borders[0] : undefined;
            if (!neighbour) throw new Error('No neighbour found');


            return getJSON(``,
            'Country not found'
            );
        })
        .then(data => {
            renderCountry(data, 'neighbour');
        })
        .catch(err => {
        console.error(`${err}`);
        renderError(`Something went wrong, ${err.message}.Try again!`);
    })
        .finally((countriesContainer.style.opacity = 1));
    };

    btn.addEventListener('click', function () {
        getCountryData('germany');
    });

I also got stuck into learning to **Promisify** my callback functions for code efficiency as well as how the different queues (_callback and microtask_) in the **Javascript Runtime Engine** function:

    setTimeout(() => console.log('0 sec timer'), 0);
    Promise.resolve('Resolved promise 1').then(res => console.log(res));

    // Start by creating a new promise using the Promise constructor, so it's just a js object
    // The promise constructor takes only one argument, and that is the "Executor Function"
    // The Executor Function will take two arguments, the resolve & reject functions
    const lotteryPromise = new Promise(function (resolve, reject) {
        setTimeout(function () {
            if (Math.random() >= 0.5) {
            // resolve marks the promise as fulfilled
            // resolve() takes the fulfilled value of the promise to be consumed with .then()
            resolve('PROMISE RESOLVED. ASSUME THE POSITION');
    } else {
            // reject marks the promise as rejected
            // reject() takes the error message that I later want to be used by the catch()error handler
             // I can also create a new error object to simulate a REAL error
            reject(new Error('PROMISE UNRESOLVED. YOU LOSE, PUNY HUMAN'));
            }
        }, 2000);
    });

Finally, I _really_ got stuck in to learning about **Async/Await**, as well as the 3 different **Promise Combinators**(_all, race, allSettled_) and their use-cases. Holy fuck, man, _promises are legit so useful_, and if I never have to write another AJAX Request I'll be a happy man - that shit felt like learning CSS floats all over again. For real, though, I've really enjoyed this course so far, and I've been learning so much by staying consistent with the coding. Who woulda' thought the trick to learning to code is the same as getting big at the gym: **consistency**.

Also, I'm leaving out the API in my code examples because IDK if I'm even allwoed to share that since it's not, like, _my_ API.. That said, check out my **Immediately-Invoked Function Expression** _that also humbled the fuck out of me because I forgot these even fucken existed lmao_:

    (async function () {
            const res = await Promise.race([
            getJSON(``),
            getJSON(``),
            getJSON(``),
        ]);
        console.log(res[0]);
    })();

**Link to work:** [Asynchronous Javascript - Promises, Async/Await, and AJAX](https://github.com/Praeda822/Javascript-Notes/blob/master/16%20Asynchronous%20Javascript/script.js)<br>
**Link to work:** [Dodgy Rock, paper, scissors game](https://github.com/Praeda822/RockPaperScissors)<br>
**Link to work:** [Even dodgier connect4 game that isnt finished](https://github.com/Praeda822/Connect4)<br>
**Link to work:**[Front-end Mockup UI Design & chart.js experimentation](https://github.com/Praeda822/PK_RE_Project)<br>
