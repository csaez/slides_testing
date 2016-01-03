class: center, middle, inverse
# Testing as a Medium

---
# Who am I?

- .big[CESAR SAEZ]
- Character TD @ Animal Logic.
- Free and open source software enthusiast.
- All things Python.
- Music lover.
- Developer wannabe.
- [@csaezmargotta](https://twitter.com/csaezmargotta) (twitter)
- http://cesarsaez.me

---
# Agenda

1. What is this talk about?
2. Testing and Technical Artists
3. Beyond the quality gate
4. Test-last vs Test-driven
5. Dealing with dependencies
6. Testing existing/legacy projects

---
class: center, middle, inverse

# What is this talk about?

---
# This is *not* about:

- *Agile* dogmas/methodologies.

--

- A tutorial on procedures.

--

- Language/framework specific.

--

- Me lecturing you.

---
# This is an *open discussion* on:

- What do we understand by testing.

--

- What are the benefits.

--

- What are the costs.

--

- Where are we in terms of testing.

--

- Why are we (not) embracing testing.

--

- What can we do to improve the current situation.

---
class: center, middle, inverse

# What is testing?

(unit testing, integration testing, exploratory testing, usability testing,
performance/load testing, anything!)

---
# Traditional approach

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
# Traditional approach

What are the benefits *from a developer POV*?

- Enable refactoring
- Avoid regressions bugs .red[*]
- ?

.footnote[ .red[*] Or at least reduce the likelihood of a regression.]

--
> ... althought it seems to add some overhead to the development proccess
> by adding an extra "phase" after the problem has been solved (similar to
> documentation).

---
class: center, middle, inverse

# Beyond the quality gate

---
# Testing as a medium

--

> Exploratory testing is simultaneously *learning about the system* while
> designing and executing tests, *using feedback from the last test to inform
> the next*.
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

# Test-last vs Test-driven

