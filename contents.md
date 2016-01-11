class: center, middle, inverse
# Testing as a medium

---
class: whoami

# Who am I?

- Cesar Saez
- Character TD @ Animal Logic.
- Free and open source software enthusiast.
- All things Python.
- Music lover.
- Developer wannabe.
- http://cesarsaez.me
- [@csaezmargotta](https://twitter.com/csaezmargotta) (twitter)

---
# Agenda

1. Introduction
2. Testing and Technical Artists
3. Automated testing
4. Beyond the quality gate
5. Test-driven development
6. Study case
7. Legacy projects
8. Conclusions

---
class: center, middle, inverse

# What is this talk about?

---
# This is *not* about

- *Agile* dogmas/methodologies.

--

- A tutorial on procedures.

--

- Language/framework specific.

--

- Me lecturing you.

---
# This is an *open discussion*

- What do we understand by testing.

--

- What are the benefits.

--

- What are the costs.

--

- Where are we in terms of testing.

--

- What can we do to improve the current situation.

---
class: center, middle, inverse

# What is testing?

(unit testing, integration testing, exploratory testing, usability testing,
performance/load testing, anything!)

---

# Testing

According to Wikipedia:

> Software testing is an investigation conducted to *provide stakeholders with
> information about the quality* of the product or service under test.

--

mmm.... what about tests:

> A test is an *experiment* designed to *reveal information* or answer a
> specific question about the software or system.

--

### tl;dr: make sure the system works as expected.

---
class: center, middle, clear

![cientific method](./images/scientific_method.png)

---
class: center, middle, clear

# Do we test?

---
class: center, middle, clear

## Of course we do!.red[*]

_ .footnote[.red[*] "It works in my computer".]_
---
class: center, middle, inverse

# Automated testing

---

# Automated testing

.big[What are the benefits *from a developer POV*?]

--

- Enable refactoring

--

- Avoid regressions bugs .red[*]

.footnote[ .red[*] Or at least reduce the likelihood of a regression.]

--

> ... althought it seems to add some overhead to the development proccess
> by adding an extra "phase" after the problem has been solved (similar to
> documentation).

---
class: center, middle, clear

![Who needs testing?](images/no_testing.jpg)

---
class: center, middle, inverse

# Beyond the quality gate

---
# Testing as a medium

--

> Testing is simultaneously *learning about the system* while designing and
> executing tests, *using feedback from the last test to inform the next*.
> .right[Elisabeth Hendrickson]

--

What about this one?

> Testing is the *medium in which solutions are developed*. The value of our
> delivered solutions depend upon how well we understand and utilize that medium.
> .right[Paul Carvalho]

---
class: center, middle, clear

![Exploratory testing](./images/ET_learning.png)

---
class: center, middle, inverse

# Test-driven development

---
class: center, middle, clear

![TDD cycle](./images/tdd_cycle.png)

---

# Test-driven development

Benefits *from a developer point of view*:

- All the previous benefits plus...

--

- Leads to better design. .red[*]

.footnote[.red[*] More on this in the next slide.]

--

- Inform us where to go next.

--

- Up to date sample code (in form of tests).

--

- Demostrate concrete progress.

--

- It's fun!

---
class: center, middle, inverse

# Study Case: *AL's website*

[![http://www.animallogic.com](images/al_greeting.png)](http://www.animallogic.com)

---

# Study Case: *AL's website*

.big[Greeting onLoad (javascript):]

```javascript
function displayTimeofDayGreeting() {
    var e = new Date,
        t = e.getHours(),
        n = e.getMinutes(),
        r = "";
    (t > 5 || t == 5 && n >= 30) && t < 12 ? r = "morning" : t < 17 ? r = "afternoon" : t < 22 ? r = "evening" : r = "night";
    this.$el.find(".doodle").each(function() {
      var e = $(this);
      e.attr("data-timeofday") != r && e.remove();
    })
}
```

.footnote[.red[*] Production code (likely untested)]

---

# Study Case: *AL's website*

```javascript
function getTimeKey(date) {
    var t = date.getHours(),
        n = date.getMinutes(),
        r = "";
    (t > 5 || t == 5 && n >= 30) && t < 12 ? r = "morning" : t < 17 ? r = "afternoon" : t < 22 ? r = "evening" : r = "night";
    return r;
}
function displayTimeofDayGreeting() {
    var key = getTimeKey(new Date);
    this.$el.find(".doodle").each(function() {
      var e = $(this);
      e.attr("data-timeofday") != key && e.remove();
    })
}
```

.footnote[.red[*] Testable code (decoupled, a.k.a. _"pure"_ function)]

---
class: center, middle, clear

## Front-end devs have no idea...
Are you sure? What about a simple "hello world" program?

---

# Homework: *hello_world.py*

```python
#!/usr/bin/env python

if __name__ == "__main__":
    print "Hello, world!"
```

- Is this a good design?
- Is it testable?
- How would you do it?

---

class: center, middle, inverse

# Legacy projects

---

# Test-last development

### Before to begin:

--

- What are the unknown/hidden dependencies/pre-requisites?

--

- Are there any specific environment requirements to mock/simulate?

--

- Can we change code?

--

- Is the code testable in its current status?

--

- *Focus on what is possible* rather than what isn’t!

---

# Test-last development

### Creating your tests:

--

- Where to start? pick a bussy code path (most bang for your buck).

--

- Create fixtures for your tests (setup, teardown).

--

- Focus on coverage instead of corner cases (avoid early refactoring).

--

- Group by pathways.

--

- Don't depend on pre-existing data (prepare test data or mock all the things).

--

- Remove dead/unused code.

---
class: center, middle, inverse

# Ultimately, it's not about us!

---

# Closing thoughts

- Testing is a tool to meassure the quality of the software/library/system.

--

- Without data/reports on the health and status of the project, it is pretty
  hard to take any kind of long-term decision.

--

- We are already testing, manual testing.

--

- Automated testing *is not a big deal*, think of it as leaving footprints as
  you go, so there's no need to repeat yourself by re-doing manual testing.

--

- A reasonable test suite helps/allows refactor and prevent regressions.

--

- Test snippets can be used as a poor's man documentation.

--

- Tests can be used to explore and drive the development (its constraints usually lead to better designs).

--

- No matter what, write testable/quality code is up to you.

---
class: center, middle, inverse

# Thanks!
