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

Daniel Raniz Raneland

<ul class="list-none! columns-2">

  <li><mdi-firefox />factor10.com</li>
  <li><mdi-email />raniz@factor10.com</li>
  <li><mdi-github />Raniz85</li>
  <li><mdi-mastodon />raniz@mastodon.online</li>

  <li><mdi-firefox />raniz.blog</li>
  <li><mdi-linkedin />/in/raneland</li>
  <li><mdi-gitlab />raniz</li>
  <li>&nbsp;</li>

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
transition: fade
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

```python
def circle_area(diameter):
  radius =  diameter / 2
  return math.PI * radius ** 2
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
layout: statement
---

# Your Turn!

## https://raniz85.github.io/ceo-bowling-kata/

<p></p>

## https://github.com/tdd-starters/

---

# Intermission

- What is hard?
- How many have reached part 2 or beyond?
- How many have strictly followed the TDD cycle?

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

- What was the hardest?
- How many finished the CEO Bowling kata?
- How many have strictly followed the TDD cycle?
- Will you continue with TDD when you leave the roow?
  - Completely?
  - Now and then?

</v-clicks>

---
layout: intro
---

# Thanks!

Daniel Raniz Raneland

<ul class="list-none! columns-2">
  <li><mdi-firefox />factor10.com</li>
  <li><mdi-email />ranisz@factor10.com</li>
  <li>&nbsp;</li>
  <li><mdi-github />Raniz85</li>
  <li><mdi-firefox />raniz.blog</li>
  <li><mdi-linkedin />/in/raneland</li>
  <li><mdi-mastodon />raniz@mastodon.online</li>
  <li><mdi-gitlab />raniz</li>
</ul>

