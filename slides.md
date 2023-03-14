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

Daniel Raniz Raneland<br/>
Kodande arkitekt @ factor10

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

# Agenda

<ul>

<li class="opacity-100 text-1.3em">Introduktion av TDD</li>
<li class="opacity-30">Ensemblesession: CEO Bowling</li>
<li class="opacity-30">Lunch</li>
<li class="opacity-30">Kort mellanspel</li>
<li class="opacity-30">Parprogrammering</li>

</ul>

---
layout: center
---

# Temperaturkoll

---
layout: center
---

# Vad är testdriven utveckling?

<h3 v-click>Att låta testerna <em>driva</em> utvecklingen</h3>

---
layout: center
---

# Varför sysslar _jag_ med TDD?

<v-clicks>

- Genom att skriva testerna först blir koden per definiton testbar
- Man tvingas till att skriva _meningsfulla_ tester

</v-clicks>

---
layout: center
---

# Tre principer

<v-clicks>

- Keep It Simple, Stupid
- You Aren't Going to Need It
- Don't Repeat Yourself

</v-clicks>

<p v-click>TDD hjälper mig med <em>två</em> av dem</p>

---
layout: center
---

# Keep It Simple Stupid

Genom att låta testen driva utvecklingen inkrementellt är det enkelt att hålla ändringarna minimala och därmed hålla koden simpel.

---
layout: center
---

# You Aren't Going to Need It

Genom att inte göra större ändringar än vad som behövs för att passera alla tester förhindrar vi att vi springer iväg 
med en överkomplicerad lösning som kanske aldrig behövs.

<p v-click><em>Om inget test kräver koden - skriv den inte!</em></p>

---
layout: center
---

# TDD destillerat

<ol>
<li v-click>Skriv ett testfall</li>
<li v-click style="color: red">Få det att gå rött</li>
<li v-click style="color: green">Få det att gå grönt</li>
<li v-click>Refaktorisera</li>
<li v-click>Repetera</li>
</ol>


---
transition: fade
---

# Varför rött?


<v-clicks>

```java {all|6}
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

# Varför rött?

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

# Vad ska man testa?

<p v-click>Allting bör testas, men allting måste inte ha ett testfall</p>

---

# Vad ska man testa?

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

# Vad ska man testa?

```python
def radius(diameter):
  return diameter / 2

def circle_area(diameter):
  return math.PI * radius(diameter) ** 2
```

---
layout: fact
---

# Livedemo

---
layout: center
---

<ul>

<li class="opacity-30">Introduktion av TDD</li>
<li class="opacity-100 text-1.3em">Ensemblesession: CEO Bowling</li>
<li class="opacity-30">Lunch</li>
<li class="opacity-30">Kort mellanspel</li>
<li class="opacity-30">Parprogrammering</li>

</ul>

---
layout: center
---

# Utvärdering

- Hur gick det?
- Vad var svårt?

---
layout: statement
---

# Test är ett hantverk

---
layout: center
---

<ul>

<li class="opacity-30">Introduktion av TDD</li>
<li class="opacity-30">Ensemblesession: CEO Bowling</li>
<li class="opacity-100 text-1.3em">Lunch</li>
<li class="opacity-30">Kort mellanspel</li>
<li class="opacity-30">Parprogrammering</li>

</ul>

---
layout: center
---

<ul>

<li class="opacity-30">Introduktion av TDD</li>
<li class="opacity-30">Ensemblesession: CEO Bowling</li>
<li class="opacity-30">Lunch</li>
<li class="opacity-100 text-1.3em">Kort mellanspel</li>
<li class="opacity-30">Parprogrammering</li>

</ul>

---
layout: center
---

# TDD för fuskare

<ol>
<li v-click>Var för exalterad för att komma ihåg att skriva testet först</li>
<li v-click>Skriv lite kod</li>
<li v-click>Kom ihåg att du skulle börjat med testet</li>
<li v-click><em>Släng (eller kommentera ut) koden</em></li>
<li v-click>Skriv ett testfall</li>
<li v-click style="color: red">Se till att det går rött - av rätt anledning</li>
<li v-click style="color: green">Se till att det går grönt</li>
<li v-click>Refaktorisera</li>
<li v-click>Repetera (från 5)</li>
</ol>

---
layout: center
---

<ul>

<li class="opacity-30">Introduktion av TDD</li>
<li class="opacity-30">Ensemblesession: CEO Bowling</li>
<li class="opacity-30">Lunch</li>
<li class="opacity-30">Kort mellanspel</li>
<li class="opacity-100 text-1.3em">Parprogrammering</li>

</ul>

---
layout: center
---

# The End...

<v-clicks>

- Vad var svårast?
- Hur många har strikt följt TDD-cykeln?
- Vad blir svårast med att använda TDD "till vardags"?

</v-clicks>

---
layout: intro
---

# Tack!

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
