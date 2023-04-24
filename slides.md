---
theme: ./theme

# https://sli.dev/custom/highlighters.html
highlighter: shiki

# show line numbers in code blocks
lineNumbers: false

# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)

# persist drawings in exports and build
drawings:
  persist: false

# use UnoCSS
css: unocss

layout: intro
---

# TDD Workshop

Daniel Raniz Raneland | Nizar Selander<br />
Coding Architects @ factor10

<ul class="list-none! columns-2">

  <li><mdi-firefox />factor10.com</li>
  <li><mdi-email />raniz@factor10.com</li>
  <li><mdi-firefox />raniz.blog</li>
  <li>&nbsp;</li>

  <li>&nbsp;</li>
  <li><mdi-email />nizar.selander@factor10.com</li>
  <li><mdi-firefox />nizar.se</li>
<!--
  <li><mdi-email />raniz@factor10.com</li>
  <li><mdi-github />Raniz85</li>
  <li><mdi-mastodon />raniz@mastodon.online</li>

  <li><mdi-firefox />raniz.blog</li>
  <li><mdi-linkedin />/in/raneland</li>
  <li><mdi-gitlab />raniz</li>
  <li>&nbsp;</li>
-->
</ul>

---
layout: center
---

# Agenda

<ul>

<li class="opacity-100 text-1.3em">TDD introduction</li>
<li class="opacity-30">Ensemble session</li>
<li class="opacity-30">Lunch</li>
<li class="opacity-30">Short intermission</li>
<li class="opacity-30">Pair programming</li>
<li class="opacity-30">Closing up</li>

</ul>

---
layout: center
---

# Testing Temperature Check

---
layout: center
---

# What is Test Driven Development

<h3 v-click>Letting the tests <em>drive</em> the development</h3>

---
layout: center
---

# Why Do _I_ practice TDD?

<v-clicks>

- By writing the tests first, the code is by definition testable
- Tests are forced to be _meaningful_

</v-clicks>

---
layout: center
---

# Three Guiding Principles

<v-clicks>

- Keep It Simple, Stupid
- You Aren't Going to Need It
- Don't Repeat Yourself

</v-clicks>

<p v-click>TDD helps with <em>two</em> of these</p>

---
layout: center
---

# Keep It Simple Stupid

By letting the tests incrementally drive the implementation it is easy to keep changes minimal between each iteration and therefore keep the code as simple as possible.

---
layout: center
---

# You Aren't Going to Need It

By not making more changes to the code than is necessary to pass all the tests,
we prevent ourselves from thinking ahead and creating complex, adaptable solutions that may never be needed

<p v-click><em>If no test require the code - don't write it!</em></p>

---
layout: center
---

# TDD Distilled

<ol>
<li v-click>Write a test</li>
<li v-click style="color: red">Make it fail</li>
<li v-click style="color: green">Make it pass</li>
<li v-click>Refactor</li>
<li v-click>Repeat</li>
</ol>


---
transition: fade
---

# Why Do We Fail?


<v-clicks>

```java
class PersonTest {

  @Test
  public void testConstructor() {
    Person person = new Person("John O'Connor");
    assertNotNull(person);
  }
}
```

</v-clicks>
---

# Why Do We Fail?

```python
import unittest
from unittest.mock import MagicMock

def call_method(method, *args):
  method(*args)

class Tests(unittest.TestCase):

  def test_call_method(self):
    # Given a method to call
    mock = MagicMock()

    # when the call_method method is called
    call_method(mock, (1, 2, 3))

    # the mock is called with the expected arguments
    assert mock.called_with(1, 2, 3)

if __name__ == "__main__": 
    unittest.main()
```

---
layout: center
---

# What Should We Test?

<p v-click>Everything should be tested, but everything doesn't need a test case</p>

---

# What Should We Test?

<div style="opacity: 0">

```python
def radius(diameter):
  return diameter / 2
```

</div>

```python
def circle_area(diameter):
  return math.PI * (diameter / 2) ** 2
```

---

# What Should We Test?

```python
def radius(diameter):
  return diameter / 2

def circle_area(diameter):
  return math.PI * radius(diameter) ** 2
```

---
layout: fact
---

# Live Demo

---
layout: center
---

<ul>

<li class="opacity-30">TDD introduction</li>
<li class="opacity-100 text-1.3em">Ensemble session</li>
<li class="opacity-30">Lunch</li>
<li class="opacity-30">Short intermission</li>
<li class="opacity-30">Pair programming</li>
<li class="opacity-30">Closing up</li>

</ul>

---
layout: fact
---

# Ensemble Time!

## https://raniz85.github.io/tdd-katas/ceo-bowling/

## https://github.com/tdd-starters/

---
layout: center
---

# Evaluation

- How did it go?
- What was hard?

---
layout: center
---

<ul>

<li class="opacity-30">TDD introduction</li>
<li class="opacity-30">Ensemble session</li>
<li class="opacity-100 text-1.3em">Lunch</li>
<li class="opacity-30">Short intermission</li>
<li class="opacity-30">Pair programming</li>
<li class="opacity-30">Closing up</li>

</ul>

---
layout: center
---

<ul>

<li class="opacity-30">TDD introduction</li>
<li class="opacity-30">Ensemble session</li>
<li class="opacity-30">Lunch</li>
<li class="opacity-100 text-1.3em">Short intermission</li>
<li class="opacity-30">Pair programming</li>
<li class="opacity-30">Closing up</li>

</ul>

---
layout: statement
---

# Testing is a Craft

<!--
practice makes perfect
-->

---
layout: statement
---

# Testing is Software Development

<!--
Precis som när man startar ett nytt projekt kräver test setup
-->

---
layout: image
image: /images/cost-over-time-1.png
---

<!--
Kostnaden för att lägga till nya features ökar exponentiellt med tiden
-->

---
layout: image
image: /images/cost-over-time-2.png
---

<!--
Med bra testtäckning ökar kostnaden mycket långsammare och mer asymptotiskt
Källa: Kent Beck
-->

---
layout: center
---

# TDD For Cheaters

<ol>
<li v-click>Be too excited to remember to write the test first</li>
<li v-click>Write some code</li>
<li v-click>Remember that you should have started with the test</li>
<li v-click><em>Discard (or comment out) your code</em></li>
<li v-click>Write a test</li>
<li v-click style="color: red">Make sure it fails for the right reason</li>
<li v-click style="color: green">Make it pass</li>
<li v-click>Refactor</li>
<li v-click>Repeat (from 5)</li>
</ol>

<!--
Per kallar det Test Driven Uncommenting
-->

---
layout: center
---

<ul>

<li class="opacity-30">TDD introduction</li>
<li class="opacity-30">Ensemble session</li>
<li class="opacity-30">Lunch</li>
<li class="opacity-30">Short intermission</li>
<li class="opacity-100 text-1.3em">Pair programming</li>
<li class="opacity-30">Closing up</li>

</ul>

---
layout: fact
---

# Your Turn!

## https://raniz85.github.io/tdd-katas/

## https://github.com/tdd-starters/

<!--
Tips:
- Försök tänka produktionskod
- Fuska lite om du inte vet vart du ska börja
-->

---
layout: center
---

# If You Finish Early

- FizzBuzz
- RPN Calculator
- https://adventofcode.com
  - 2021 - day 6
  - 2021 - day 21
  - 2022 - day 7

---
layout: center
---

# The End...

<v-clicks>

- How many finished the kata?
- How many have strictly followed the TDD cycle?
- What was the hardest?
- Will you continue with TDD when you leave the room?
  - Completely?
  - Now and then?

</v-clicks>

---
layout: intro
---

# Thanks!

Daniel Raniz Raneland | Nizar Selander<br />
Coding Architects @ factor10

<ul class="list-none! columns-2">

  <li><mdi-firefox />factor10.com</li>
  <li><mdi-email />raniz@factor10.com</li>
  <li><mdi-firefox />raniz.blog</li>
  <li>&nbsp;</li>

  <li>&nbsp;</li>
  <li><mdi-email />nizar.selander@factor10.com</li>
  <li><mdi-firefox />nizar.se</li>
<!--
  <li><mdi-email />raniz@factor10.com</li>
  <li><mdi-github />Raniz85</li>
  <li><mdi-mastodon />raniz@mastodon.online</li>

  <li><mdi-firefox />raniz.blog</li>
  <li><mdi-linkedin />/in/raneland</li>
  <li><mdi-gitlab />raniz</li>
  <li>&nbsp;</li>
-->
</ul>
