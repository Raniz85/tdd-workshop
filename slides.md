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

<h1 class="max-w-625px">
Test Driven Development for Everyone
</h1>

<div class="text-black">
Daniel Raniz Raneland<br />
Coding Architect @ factor10

<div class="grid grid-cols-4 w-80% mt-10">
    <div></div><div class="col-span-2"><mdi-firefox />factor10.com</div>
    <div class="col-span-2"><mdi-email />raniz@factor10.com</div>
    <div class="col-span-2"><mdi-mastodon />raniz@mastodon.online</div>
    <div class="col-span-2"><mdi-firefox />raniz.blog</div>
    <div class="col-span-2"><mdi-linkedin />/in/raneland</div>
</div>
</div>

<div class="absolute right-20px top-90px">
    <img width="300" src="/images/about-me-qr.svg" />
    <div class="w-100% mx-auto text-center">about.me/raniz</div>
</div>

---
layout: center
---

# What is Test Driven Development

<h3 v-click>Letting the tests <em>drive</em> the development</h3>

---
layout: center
---

# Testing Temperature Check

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
layout: center
---

# Why Do Raniz practice TDD?

<div class="absolute left-10px bottom-10px text-center">
  <img src="/images/blog-benefits-of-tdd-qr.png" />
  raniz.blog
</div>

<ul>
<li v-click="1">Testable code leads to looser coupling - i.e. better maintainability</li>
<li v-click="2">Incremental problem solving</li>
<li v-click="3">Principles</li>
<li v-click="4">Tests
  <ul>
    <li v-click="5">Tests are meaningful</li>
    <li v-click="6">More tests => higher quality</li>
    <li v-click="7">Bugs are overlooked tests</li>
    <li v-click="8">Documentation</li>
    <li v-click="9">Confidence when refactoring</li>
  </ul>
</li>
<li v-click="10">Velocity</li>
</ul>

---
layout: center
---

# Some Guiding Principles

<v-clicks>

- Keep It Simple, Stupid
- You Aren't Going to Need It

</v-clicks>

---
layout: center
---

# Keep It Simple Stupid

By letting the tests incrementally drive the implementation it is easy to keep changes minimal between each iteration and therefore keep the code as simple as possible.

<p class="opacity-50%">
The safety-net built up by the tests means we can safely refactor until we are satisfied with the solution.
</p>

---
layout: center
---

# You Aren't Going to Need It

By not making more changes to the code than is necessary to pass all the tests,
we prevent ourselves from thinking ahead and creating complex, adaptable solutions that may never be needed

<p v-click class="opacity-50%"><em>If no test require the code - don't write it!</em></p>


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
````md magic-move
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
```python
import unittest
from unittest.mock import MagicMock

def call_method(method, *args):
    pass

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
```python
import unittest
from unittest.mock import MagicMock

def call_method(method, *args):
    pass

class Tests(unittest.TestCase):

  def test_call_method(self):
    # Given a method to call
    mock = MagicMock()

    # when the call_method method is called
    call_method(mock, (1, 2, 3))

    # the mock is called with the expected arguments
    assert mock.assert_called_with(1, 2, 3)

if __name__ == "__main__":
  unittest.main()
```
````

---
layout: center
---

# What Should We Test?

<p v-click>Everything should be tested, but everything doesn't need a test case</p>

---

# What Should We Test?

```rust
fn circle_area(radius: f64) -> f64 {
    radius * radius * PI
}
```

---

# What Should We Test?

```rust
fn radius_from_diameter(diameter: f64) -> f64 {
    diameter / 2f64;
}

fn circle_area_diameter(diameter: f64) -> f64 {
    let radius = radius_from_diameter(diameter);
    radius * radius * PI
}
```

---

# What Should We Test?

```rust
fn determinant3(a: f64, b: f64, c: f64, d: f64, e: f64, f: f64, g: f64, h: f64, i: f64) -> f64 {
    a * e * i + b * f * g + c * d * h - a * f * h - b * d * i - c * e * g
}

fn radius_from_points(p1: Point, p2: Point, p3: Point) -> f64 {
    // Calculate the radius given 3 points on a circle
    let d = determinant3(p1.x, p1.y, 1.0,
                         p2.x, p2.y, 1.0,
                         p3.x, p3.y, 1.0);
    let d1 = determinant3(p1.x.powi(2) + p1.y.powi(2), p1.y, 1.0,
                          p2.x.powi(2) + p2.y.powi(2), p2.y, 1.0,
                          p3.x.powi(2) + p3.y.powi(2), p3.y, 1.0);
    let d2 = determinant3(p1.x, p1.x.powi(2) + p1.y.powi(2), 1.0,
                          p2.x, p2.x.powi(2) + p2.y.powi(2), 1.0,
                          p3.x, p3.x.powi(2) + p3.y.powi(2), 1.0);
    if d == 0.0 {
        panic!("The provided points are collinear");
    }
    let cx = -d1 / (2.0 * d);
    let cy = d2 / (2.0 * d);
    ((cx - p1.x).powi(2) + (cy - p1.y).powi(2)).sqrt()
}
```

---
layout: fact
---

# Live Demo

---
layout: fact
---

# Your Turn!

## https://github.com/tdd-starters/

<br/>

## https://raniz85.github.io/tdd-katas/

<!--
Tips:
- Försök tänka produktionskod
- Fuska lite om du inte vet vart du ska börja
-->

---
layout: fact
---

# Intermission

---
layout: center
---

# Intermission

<v-clicks>

- What is hard?
- How many has finished at least 1 part?

</v-clicks>

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

# If You Finish Early

- FizzBuzz
- RPN Calculator
- https://sammancoaching.org/kata_descriptions/

---
layout: center
---

# The End...

<ul>
  <li v-click="1">How many finished the kata?</li>
  <li v-click="2">How many have strictly followed the TDD cycle?</li>
  <li v-click="3">What was the hardest?</li>
  <li v-click="4">Will you continue with TDD when you leave the room?
    <ul>
      <li v-click="5">Completely?</li>
      <li v-click="6">Now and then?</li>
    </ul>
  </li>
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
layout: intro
---

# Thanks!

<div class="text-black">
Daniel Raniz Raneland<br />
Coding Architect @ factor10

<div class="grid grid-cols-4 w-80% mt-10">
    <div></div><div class="col-span-2"><mdi-firefox />factor10.com</div>
    <div class="col-span-2"><mdi-email />raniz@factor10.com</div>
    <div class="col-span-2"><mdi-mastodon />raniz@mastodon.online</div>
    <div class="col-span-2"><mdi-firefox />raniz.blog</div>
    <div class="col-span-2"><mdi-linkedin />/in/raneland</div>
</div>
</div>

<div class="absolute right-20px top-90px">
    <img width="300" src="/images/about-me-qr.svg" />
    <div class="w-100% mx-auto text-center">about.me/raniz</div>
</div>