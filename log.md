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

#####

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
**Link to work:** [Front-end Mockup UI Design & chart.js experimentation](https://github.com/Praeda822/PK_RE_Project)<br>

### Day 38: Wednesday, 12th June, 2024

#####

**Today's Progress:** Today I focused on Modern JavaScript development, specifically the implementation of ES6 modules. I practiced successfully importing/exporting functions across different files, as well as understanding (_attempting to lol_) the complexities of bundling and transpiling code.

**Thoughts:** OK, _fuck me_, today was a _YUUUUGE_ day of theory getting stuck into the _Modern Javascript Development_ build process/lifecycle. Remember how when I was learning OOP with JS I was complaining that OOP and Javascript, whilst it works, still feels like having to do the same thing twice to accomplish a task once? _Yeah.._ it's back; it never really ended, honestly, and they call it _Transpiling/Polyfilling_. _Thank fucking god_ we live in the year of our Lord 2024AD and apparently I can use a tool for this called **Babel** and that will output for me a final javascript file ready for deployment on a server (_into prod_).

_NOW_ here's the wicked cool part: apparently I don't really have to do any of this, but I'll get to play around with NPM and install **Parcel** (_or webpack, but apparently webpack is cooked to learn_) which is a _Javascript Bundler_ that will take the javascript file produced by **Babel** and whip it up into a working model.

Fuck, man, apparently this is the _really_ important stuff so I'm stressing just a bit about it..

**Link to work:** [Modern Javascript Modules, Tooling, Implementation](https://github.com/Praeda822/Javascript-Notes/tree/master/17%20Modern%20Javascript%20Modules%20%26%20Tooling)<br>

### Days 39-45: Thursday, 13th June - Wednesday, 19th June 2024

#####

**Week's Progress:** Spent the past week diving deep into modern JS development by structuring my code using modules, transpiling and polyfilling (_Babel_), as well as using & configuring javascript bundlers (_Parcel_) to produce a final working web app. I was able to enhance it further by refactoring my code from boring old modules, to _ES6 modules_, I learned about _async/await_, linking javascript modules together, as well as the implementation of both the _Module Pattern_ and _importing/exporting_ my modules **asynchronously** (_fuck this word lol_).

**Thoughts:** Another absolute _banger_.. Yes, of course it was sarcasm! Something very import I learned this week was a key difference between ES6 modules and scripts:
<br><br>

**In _ES6 Modules_, the .this keyword is always "undefined" at the top level, and I can also use the _import/export_ syntax**

<br>

**In Scripts, the .this keyword will point to the _.window()_ object, and I am also unable to _import/export_ except at the very top level (_outside of any function/if block_) and _ALL_ my imports are hoisted to the top of the file since _importing always occurs first in modules_**

<br>

Now with that very import reminder out of the way, _what a fucking week, man.._ OK, it wasn't _that_ bad, and I actually enjoyed a lot of the content, especially learning how all of this module importation/exportation is done asynchronously, so _through a **WEB API**_, which means it's a shit load of back & forth, but it doesn't block my code if I fuck it up too badly..._nah, I'm just kidding_, it totally blocks up the code when I fuck it up.

_But PK_, you say, _What could cause the code to shit the bed?_

WELL, calling an asynchronous function will **always return a _Promise_**, and those promises **need** to be handled.._roughly_. For instance:

    async function x(){}
    console.log('Start fetching..');
    const res = await fetch('https://jsonplaceholder.typicode.com/posts');
    const data = await res.json();
    console.log(data);

    const lastPost = getLastPost();
    console.log(lastPost); // Pending Promise

I'm not going to lie, it did take me a good minute (_lmaoo_) to get my head around handling promises, especially syntax-wise as after a while of staring at _fetch/await_ my eyes just sort of glazed over.. But it's not even that hard since the responses are handled by Javascript's built-in _.JSON()_ object and converted to a nice JSON string for me to manage - how good is that.

We really focused in on _scoping_, though, in regards to learning & implementing modules, since the whole point of this section is for us to try & understand how to essentially _build_ our own _APIs_, as well as how to _expose_ them by linking them together with other modules. Overall the whole point of this is for code reuability, and I can get that, but _fuck me dead_ it's a lot to get my head around trying to figure out where everything should go and how I should refactor it when my (_albeit very shitty_) "code" (_I'm just being unnecessarily hard on myself, or so the mrs reckons_) is working to begin with....

But to end on a good note, I _did_ get some _incredible_ notes as well as a new perspective for writing code, and a new approach for how to write & structure that code, as well - reminds me of when I was learning _HTML/CSS_ and the concept of the _Block Element Model(Modifier)_, or **BEM**, was introduced to me.

**Link to work:** [Modern Javascript Modules, Tooling, Implementation](https://github.com/Praeda822/Javascript-Notes/tree/master/17%20Modern%20Javascript%20Modules%20%26%20Tooling)<br>

### Days 46-53: Thursday, 20th June - Thursday, 27th June 2024

**Week's Progress:** This past week, I started the final project of this Javascript course: the Forkify project, which focuses on building a recipe search and management web application. This project involves several key programming concepts, including MVC (Model-View-Controller) architecture, asynchronous programming with API interactions, state management, pagination, and DOM manipulation.

**Thoughts:** This past week has been _demoralizing_, to say the least..

I was keen as a bean to rip into this last part of the course, thinking to myself _man I'm so close to finishing I can taste it_, especially since we started the section of the project off with some theory & design, mapping out the **User Stories**, **Features**, as well as another one of those bubble-map flow-charts to outline **code structure**, **maintainability**, and **scalability**. But _booooy_ how wrong I was about the depth of the project scope.

I started off the project by (_attempting_) to seperate the project code into its now 3 different constituents: **model**, **view**, & **controller**, respectively. All's well & good so far. Then I created a **state** variable, that was essentially going to hold the literal application state (_I've been calling it the fake DOM_), and then we broken up the code blocks, again, into the **three** individual components of the _MVC Architecture_: the **Business Logic**, the **Application Logic**, and the **Presentation Logic**. Again, so far so good..

And here is where things got a bit fucky for me, personally, and according to the course's Q&A, I am, and have been, _not_ the only one to experience this feeling of _What the actual **fuck** is going on, here_ in regards to this project, specifically. It's been extremely difficult for me to abstract the, _now 11_ different javascript files and how they're all linked together - I've felt completely overwhelmed with it, and genrally lost in the code. I'm really annoyed with myself for it, since despite doing this for **HOURS** every single day, I'm still struggling a bit, and I get that I'm new at all of this, but I've had to humble myself and, despite not really knowing what's going on (_I know WHY things are working, though, if that makes sense.._), I've been plowing ahead just trying to finish this off, so, _tbh_ I will _definitely_ be reviewing this entire project in month 3 of this challenge.

_Fuck me_, man, MVC architecture is..really difficult the first go 'round, you know?

**Link to work:** [Forkify App](https://github.com/Praeda822/Javascript-Notes/tree/master/18%20Forkify%20App)<br>

### Days 54-57: Friday, 28th June - Monday, 1st July

**Week's Progress:** I've spent the past 3 days wrapping up the Javascript Fundamentals course, which is now **DONE**. Implemented the final logic for the user submitted recipes to function properly, as well as more black magic with template literals & AJAX Calls for JSON promises. Also made a to-do list of features I want to implement on the app down the road (_like when I can actually fucking abstract the scope of half the shitshow that is **MVC Architecture**_).

I also made a shitty little weather app that pulls data from an online weather WebAPI (_that's supposedly free.._) and displays it on my page when the user clicks a button. It's nothing special, but I'm sure I'll have use of it in the future (_lmao_).

Finally, I tried implementing NPM stuff into my weather app project, but when I refactored it for the MVC architecture shit the whole fucking app just fell apart, and now I've got _SEVEN different fucking files_ that, for whatever reaason, don't work together at all. And the best part? **No errors**. Fucken-A. **>\_>**

**Thoughts:** I'm still super annoyed with myself since I still feel really lost with the **Forkify Project**. I did discover the wonderful world of _JSCDocs_, however, but...that still didn't really help me all that much with understanding the Forkify project better.

I'm noticing that I'm becoming extremely proficient at reading, as well as understanding, the code infront of me, but then I somehow manage to fuck myself up and get lostr in the abstractions of which files point to which functions and why - it's so hard to visually imagine & remember _where the fuck everything is_ and then I've got to actually _write_ the code ontop of it. Holy fucking fuck, dude, what am I missing here that I'm making it so hard for myself to understand the **SCOPE** of the project? How the _fuck_ do people keep track of all this shit, even _WITH_ JSDocs???

    /**
    * Represents the state of the application.
    * @typedef {Object} State
    * @property {Object} recipe - The currently selected recipe.
    * @property {Object} search - The search state.
    * @property {string} search.query - The search query.
    * @property {Array} search.results - The search results.
    * @property {number} search.page - The current page of search results.
    * @property {number} search.resultsPerPage - The number of search results per page.
    * @property {Array} bookmarks - The bookmarked recipes.
    */

    /**
    * The application state.
    * @type {State}
    */
    export const state = {
    recipe: {},
    search: {
        query: '',
        results: [],
        page: 1,
        resultsPerPage: RES_PER_PAGE,
    },
    bookmarks: [],
    };

    /**
    * Creates a recipe object based on the provided data.
    *
    * @param {Object} data - The data object containing recipe information.
    * @returns {Object} - The created recipe object.
    */
    const createRecipeObject = function (data) {
    const { recipe } = data.data;
    return {
        id: recipe.id,
        title: recipe.title,
        publisher: recipe.publisher,
        sourceUrl: recipe.source_url,
        image: recipe.image_url,
        servings: recipe.servings,
        cookingTime: recipe.cooking_time,
        ingredients: recipe.ingredients,
        // this is a REALLY NICE WAY of conditionally adding properties to an object
        // if recipe.key is a falsy value, nothing happens since && short-circuits
        // if recipe.key DOES exist, then the key object is returned and displayed as if the values were on the outside
        ...(recipe.key && { key: recipe.key }),
    };
    };

**THAT** point of the code above is really where I started to get fucked up, when we created that _fake DOM_ to ultimately use it as a comparison/data validator for the _real DOM_ by comparing the missing values between the two, calling a _.render()/.update()_ method to update page contents, dynamically & responsively,and just..reorganising all the data:

    render(data, render = true) {
        // Check if data is empty or an empty array
        if (!data || (Array.isArray(data) && data.length === 0))
        return this.renderError();
        this._data = data;
        const markup = this._generateMarkup();

        // If render is false, return the markup string
        if (!render) return markup;

        // Clear the parent element and insert the markup into it
        this._clear();
        this._parentElement.insertAdjacentHTML('afterbegin', markup);
    }

_Fuck_, again, I just feel so lost in the data flow it's crazy. Idk, it's hard for me to explain what I don't understand since I feel like I don't understand anything, anymore..I just can't remember where all my functions are and what the _fuck_ they do at any one given time..

In even more _tragic_ news, I decided to strike an attempt at making an online **Weather App** that pulls data from a WebAPI and displays it on the screen when the users submits text in an input field. Pretty basic shit, _yeah_? It was **significantly** easier just managing the one _index.js_ file, and I didn't have any issues with fucking around with the data up until I tried to reuse my _.getJSON()_ function from the **Forkify app**:

    /**
    * Fetches JSON data from the specified URL.
    *
    * @param {string} url - The URL to fetch the JSON data from.
    * @param {string} [errorMsg="Something went wrong.."] - The error message to display if the fetch fails.
    * @returns {Promise} A promise that resolves to the JSON data.
    * @throws {Error} If the fetch fails, an error is thrown with the specified error message and status code.
    */
    const getJSON = function (url, errorMsg = "Something went wrong..") {
    return fetch(url).then((response) => {
        if (!response.ok) throw new Error(`${errorMsg} (${response.status})`);
        return response.json();
    });
    };

And guess what the problem was almost the _entire fucking time_????<br>

    async function getWeatherData(city) {
    return getJSON(
        `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${API_KEY}`
    );
    }

**I DIDN'T RETURN THE FUCKING JSON CALL. AAAAAAAAAA**

The last totally _shit_ part was when I tried to get _Chat GPT_ to help walk me through how to refactor my code for the **MVC Architecture**. Guess what (_again_)? Broke the _entire fucken project_, and I, _again_ lost sight of the project scope. I'm never asking _Chat GPT_ to advise me of libraries to use, and NPM still managed to totally break my entire fucking project. Also, MVC _can eat my ass_.

Other than that, though, I actually..had a lot of fun with the **Weather App**, since I understood what the fuck was going on with just **ONE FILE**.

**Link to work:** [Forkify App](https://pk-forkifyrecipe.netlify.app)<br>
**Link to work:** [Weather App](https://pk-weatherapp.netlify.app)<br>

### Day 58: Tuesday 2nd July

**Today's Progress:** Today I used Javascript to build a calculator, a stopwatch, and a digital clock that updates in real-time (_NO API CALLS_). I also learned about a new method today, _eval()_, which takes a value and literally just evaluates it. FInally, I refactored all of the code in my 3 projects into reusable, modular ES6 classes with (_what I think is..?_) proper data encapsulation, respectively.

**Thoughts:** It was nice to have a break today, _especially_ from the MVC nonsense of the course, and although I made 3 seperate (_albeit shitty_) little apps, I still felt like I was procrastinating..because _I fucken was_. It was good to get some practice making ES6 classes again, though, and since I don't need to worry about MVC I can just instead focus on the code & its data flow. The more times I refactor things, the more I start to understand modular patterns, but that's all going to mean _fuckall_ if I don''t apply it to _imports/exports_ and _promises_, etc..

And all it's taken for it to all make sense again has been _10 hour days_ on the laptop for the past almost 2 months. I want to spend this last coming month before college starts building something cool that I can proud of, but I'm not sure what, yet..

**Link to work:** [PKs JS Calculator](https://pk-jscalculator.netlify.app)<br>
**Link to work:** [PKs Stopwatch](https://github.com/Praeda822/JS-Components/tree/master/Stopwatch)<br>
**Link to work:** [PKs Digital Clock](https://github.com/Praeda822/JS-Components/tree/master/Digital%20Clock)<br>

### Days 59-61: Wednesday 3rd July - Friday, July 5th

**Past Day's Progress:** Spent the last 3 days making another mockup design of a website for a Hotel business, Ratto's.

**Thoughts:** Officially 2 months straight of coding _every single day_. So far I've managed to build 6 different little web apps, and I've learned an unbelievable amount of programming and design to the point now where the headaches are a _near daily_ occurence. I finished the Javascript course, desptie feeling lost af in the final recipe book project (_especially regarding state management.._) but I _did_ manage to get my head around it eventually. Which means now the biggest struggle/stressor has been learning, and understanding (_or at the very least attempting to.._) **MVC Architecture**. FML.

So I decided to take a (_well deserved_) break from grinding Javascript foundational concepts and mocked up a front-end design for a Hotel called _Ratto's_, which is just purely _HTML & SCSS_, with my primary focus on being remembering how to use and properly utilise flexbox, so no grid-template layouts in this one. Man, it's crazy now how easy it to write CSS and play around with flexbox, and I'm amazed that I still remember the trick with font-sizing for responsivity with Web Apps, in that I mean you set the font to _62.25%_,consequently defining my base font-size as _1rem = 10px_ which makes sizing SO EASY, since all I had to do to make the entire page responsive was to readjust the sizing of my font!! I know, _clever_, no?

That said, though, I really need to get back into the Javascript swing of things, since if I really _am_ going to be working as a full-stack web Developer/Web Designer, then I need to _practice, practice, practice_ making APIs to retrieve data from an object somewhere out on the internet.. I also went to my local community college's information session for the 6-month programming course I've enrolled in, and I'll be learning **.NET** & **C#**, as well as **React Native**, which sounds like it's going to be sick!! I think with **C#** I'll be able to use it as a backend for future projects with Javascript on the front-end, however I really should learn **PHP** and **Python**.. Fuck man there's so much I need to know before I feel like I can even warrant applying for jobs _lol_. _Lmao_, even.

**Link to work:** [PKs JS Calculator](https://pk-jscalculator.netlify.app)<br>
**Link to work:** [PKs Stopwatch](https://github.com/Praeda822/JS-Components/tree/master/Stopwatch)<br>
**Link to work:** [PKs Digital Clock](https://github.com/Praeda822/JS-Components/tree/master/Digital%20Clock)<br>
**Link to work**: [Weather App](https://pk-weatherapp.netlify.app)<br>
**Link to work**: [Forkify CRUD Recipe App](https://pk-forkifyrecipe.netlify.app)<br>

### Days 62-72: Saturday, July 6th - Tuesday, July 16th

**Past Week's Progress:** I spent this past week refreshing myself on CSS Flex & CSS Grid fundamentals, as well as punishing myself for **6 (_almost 7_) days straight**, wrangling with the hot garbage that is **React**.

**Thoughts:** How ironic is it that I felt that I needed a break from the Javascript, so I smashed out some CSS Grid & Flex projects, _Hotel Los Rattos_ & _Kelly's Expensive Dirt Sales_, and I had so much fun doing them, especially doing the initial layout setup using grid, then maiing my little sub-grids inside of them to place my elements exactly where I want them. Reminded me of when I did my mate's website, [Homescaped](https://homescaped.com.au/), in that I used a sass grid layout setup for it, too.

Which brings me to my next, _and current_, issue: **React fucking sucks**. Seriously. This is now the 4th time I've used React, and it's the fourth time I've wanted to push shards of glass into my eyes. OK, so some context:

I started last week off kind of _floating_, uneusre of what I should and/or ought to do next to solidify my Javascript abilities, but last week I _really_ didn't want to look at Javascript..but I let the mrs convince me otherwise, that I _could learn React_, that I was worried over nothing and was, perhaps, just overthinking the issue at hand. And me, _being fucking me_, decided to throw myself into the proverbial deep end of it all by trying to follow a tutorial online to make an online banking/finance app thing, and it genuinely looked pretty schmik, and I was actually pretty excited to build it all.
<br>
_mAyBe tHiS tImE iT wIlL bE dIfFeReNt HaHAHAa_
<br>
I even broke it down right down to the single (_AND REQUIRED_) line of code. look at this fucking horseshit:

[UseRef only works in Client Components. Add the 'use client' directive at the top of the file..](https://github.com/Praeda822/pkbanking/commit/66384831a2e8e8ee5612b6e6879c95dccdb3e8e8)

    "use-client";

    import { Chart as ChartJS, ArcElement, Tooltip, Legend } from "chart.js";
    import { Doughnut } from "react-chartjs-2";

    ChartJS.register(ArcElement, Tooltip, Legend);

    const DougnutChart = ({ accounts }: DoughnutChartProps) => {
    const data = {
    datasets: [
        {
            label: "Banks",
            data: [1250, 2500, 3750],
            backgroundColor: ["#0747b6", "#2265d8", "#2f91fa"],
        },
    ],
    labels: ["Bank 1", "Bank 2", "Bank 3"],
    };
    return <Doughnut data={data} />;
    };

    export default DougnutChart;

It genuinely did not matter whether I used the _DougnutChart_ import or the _CountUp_, both of them kept shitting out the exact same error on line 363 of the bundled Javascript because _var useRef="Null"_, whatever the fuck that means, but I've got a funny feeling that it's not supposed to be equal to null.

Queue to me spending, what, **3-4 fucking days** of googling and researching shit, but I still can't get it to work! I even copy/pasted the exact code from the creator's GitHub; Guess what? **Didn't fucking work**. Not even that, I opted to ask the LLMs what the fucking go with it is, surely I just fucked up with a typo of a forgotten parentheses somewhere, _right_? ChatGPT didn't know, Claude said it was right & tight, CoPilot reckons it should be working, and my own personal local model _also_ said that it should be working. I asked online, provided examples of my code, and _lo-and-behold_ it still. doesn't. fucking. work.

Now I feel like a fucking goose since I've wasted a week when I could have been just doing shit the way I fucking know how to using SASS and my own grid setup to position my elements exactly how, and where, I want them on the screen, whilst keeping the entire thing responsive. Which _fucking dickhead_ said it would be a good idea to need **300mb+** of bullshit just to center a div!? If all the modern web apps are built using this shit, since it would appear that React/Typescript is the most (((_popular_))), then it's any wonder nothing fucking works anymore. Even VSCode wouldn't format the React/Typescript properly that's how fucked it all is: _unintuitive abstract dogshit_, and now I just feel deflated & burned out since apparently _it just werks_ for every other dickhead on the internet.

Fuuark I'm looking forward to starting College & learning C# - Vanilla Javascript is chill as, all it's frameworks/libraries etc are just a fucking mess.

**Link to work:** [Kelly's Expensive Dirt Sales](https://pkdirt.netlify.app/)<br>
**Link to work:** [Hotel Ratto's](https://rattos.netlify.app)<br>
**Link to work:** [God I fucking detest React](https://github.com/Praeda822/pkbanking/)<br>
