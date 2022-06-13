<!--

author:   André Dietrich, Sebastian Zug
email:    andre.dietrich@informatik.tu-freiberg.de & sebastian.zug@informatik.tu-freiberg.de
version:  0.0.1
language: en
narrator: US English Female

logo:     https://assets-global.website-files.com/5e9996a6531fea7d1003b18e/62247118d91be13aa5de577f_Group%201919-min.png

comment:  Presentation and interactive demonstration of LiaScript at the
          "We Are Developers 2022" conference in Berlin.

import:   https://raw.githubusercontent.com/liaTemplates/plantUML/master/README.md
          https://raw.githubusercontent.com/liaTemplates/AVR8js/main/README.md
          https://raw.githubusercontent.com/LiaTemplates/ABCjs/0.0.2/README.md
          https://raw.githubusercontent.com/liaTemplates/TextAnalysis/main/README.md
          https://raw.githubusercontent.com/LiaTemplates/algebrite/0.2.1/README.md
-->

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/LiaScript_WeAreDevelopers2022/master/README.md#1)

# LiaScript - Interactive Markdown for Education & Documentation

---------------------------------------------------------------------

This presentation illustrates the vision of _Open Educational Ressources_ and its application on LiaScript. The document was used during a session of WeAreDevelopers in Berlin on 14th June 2022.

_The sources of the presentation can be found at [Link](https://github.com/LiaPlayground/LiaScript_WeAreDevelopers2022) zu finden._

------------------------------------------------------

André Dietrich, Sebastian Zug

Faculty of Mathematics and Computer Science

TU Bergakademie Freiberg

[sebastian.zug@informatik.tu-freiberg.de](mailto:sebastian.zug@informatik.tu-freiberg.de)

------------------------------------------------------


## Motivation

                                      {{0-3}}
> __Question:__ Who already has experience in teaching (in school or university) OR writes tutorials for software?

                                      {{1-3}}
> __Question:__ What was your hope before spending hours sifting through material, organizing and animating?

                                      {{2-3}}
********************************************************************************

Developing learning content with other contributors

<!--
style="width: 100%; max-width: 860px; display: block; margin-left: auto; margin-right: auto;"
-->
```ascii

Version 1.0                            Version 1.1
+---------------------------+          +---------------------------+
| Course  German Literatur  |          | Course  German Literature |
| Authors John Muster       | "Error"  | Authors John Muster       |
|                           |------->  |         Angelika Maier    |------> ....
|~~~~~~~~~~~~~~~~~~~~~~~~~~~|          |~~~~~~~~~~~~~~~~~~~~~~~~~~~|
| In 1756 Goethe visited    |---.      | In 1786 Goethe visited    |--.
| Italy ...                 |   |      | Italy ...                 |  |
                                |                                     |    Version 1.1
                                |                                     |    +----------------------------+
                                |                                     |    | Course  німецька література|
                                |                                     |    | Authors John Muster        |
                                |                                     .--> |         Angelika Maier     |
                                |                                          |         Стів Грей          |
                                |                                          |~~~~~~~~~~~~~~~~~~~~~~~~~~~~|
                                |                                          | У 1786 році Гете здійснив  |
                                |                                          | подорож до Італії ...      |
                                |       Version 1.0
                                |      +---------------------------+
                                |      | Course  Goethe & Schiller |
                                |      | Authors John Muster       |
                                .-->   |         Angelika Maier    |--+-->
                                       |~~~~~~~~~~~~~~~~~~~~~~~~~~~|  |
                                       | The correspondence during |  |
                                       | the Italian journey ...   |  |
                                                                      :
```
*Versions of the freely available teaching content of a course and its reuse in other courses*.


********************************************************************************

### Open Educational Resources

>  **Open Courseware / Open Educational Resources** ... teaching, learning and
> research materials in any medium, digital or otherwise,that reside in the
> **public domain** or have been released under an open license that permits
> no-cost access, use, **adaptation** and **redistribution** by others with no or 4
> limited restrictions. Open licensing is built within the existing framework of
> intellectual property rights as defined by relevant international conventions
> and respects the authorship of the work
>
> -- UNESCO 2002 Forum on the Impact of Open Courseware for Higher Education in Developing Countries [(Link)](https://unesdoc.unesco.org/ark:/48223/pf0000128515)


### Challenges and opportunities of OER

                                    {{0-1}}
********************************************************************************

General Misunderstanding of OER
===================================

Types of files labeled with "OER" on TU Bergakademie's servers:

<!-- data-type="BarChart"
data-title="Ratio of different data formats of 'OER' materials at TU Bergakademie Freiberg"
data-show="true"
data-xlabel="Datentyp"
data-ylabel="% of Anzahl" -->
| Dateityp | Anzahl |
| -------- | ------ |
| `pdf`    | 5242   |
| `jpg`    | 1040   |
| `mkv`    | 873    |
| `mp4`    | 586    |
| `png`    | 494    |
| `zip`    | 443    |
| `html`   | 387    |
| `docx`   | 376    |
| `pptx`   | 245    |
| `xlsx`   | 191    |

********************************************************************************

                                   {{1-2}}
********************************************************************************

Specific problems
===================================

| requirement                          | meaning                                             | Challenges                                           |
| ------------------------------------ | --------------------------------------------------- | ---------------------------------------------------- |
| `storing/copying`                    | downloading, storing and copying                    | closed learning management systems                   |
| `use`                                | use in learning context                             | different learning platforms                         |
| `process`                            | transformation                                      | missing standards                                    |
| `adapting/mixing`                    | extraction and combination                          | commercial software products, limited digital skills |
| `disseminate` / `version management` | (digital) publication of                            |     limited digital skills                                                 |
| `identify`                           | <!-- Style="color:red" -->  find relevant materials | bunches of OER data bases                                                      |


*_(Extended) definition of OER according to 5V Modell described by Jöran Muuß-Merholz und Jörg Lohrer für [open-educational-ressources](https://open-educational-resources.de)_*

> __Surprise:__ A simple text document containing Markdown content and some training would solve the problems.

********************************************************************************

                                   {{2-3}}
********************************************************************************

... but what about the content?
===================================

> ... no one will give you the teaching award for static web pages!

<div id="example1">
<wokwi-led color="red"   pin="13" label="13"></wokwi-led>
<wokwi-led color="green" pin="12" label="12"></wokwi-led>
<wokwi-led color="blue"  pin="11" label="11"></wokwi-led>
<wokwi-led color="blue"  pin="10" label="10"></wokwi-led>
<span id="simulation-time"></span>
</div>

```cpp
byte leds[] = {13, 12, 11, 10};

void setup() {
  Serial.begin(115200);
  Serial.print("Hello WeAreDevelopers!");
  for (byte i = 0; i < sizeof(leds); i++) {
    pinMode(leds[i], OUTPUT);
  }
}

int i = 0;
void loop() {
  digitalWrite(leds[i], HIGH);
  delay(250);
  digitalWrite(leds[i], LOW);
  i = (i + 1) % sizeof(leds);
}
```
@AVR8js.sketch

> __Challenge:__ We have to bridge the gap between usability and interactive content.

********************************************************************************

## LiaScript

<!--
style="width: 100%; max-width: 860px; display: block; margin-left: auto; margin-right: auto;"
-->
```ascii
LiaScript = free
            interactive learning materials,
            organized by a version control system,
            represented in a human readable manner,
            executed in a server-less infrastructure.                           .
```
*Vision of LiaScript.*


<!--
style="width: 100%; max-width: 860px; display: block; margin-left: auto; margin-right: auto;"
-->
```ascii
   +---------------------+
   | # Digital Systems V1|\
 +--------------------+  +-+
 | # Digital Systems  |\
+------------------+  +-+
| # Digital Systems|\                                      .-----------.
| (SoSe 2021)      +-+                              ╔══════|   LMS  X  |══════╗
|                    |  --------------------------> ║      '-----------'      ║
| ## Task 1          |                              ║ Digital Systems 2021    ║
|                    |                              ║                         ║
| + Implement ...    | --------------+              ║ import numpy as np      ║
|                    |    Trans-     |              ║ ...                     ║
|                    |    formation  |              ╚═════════════════════════╝
+--------------------+               v
                                .-,(   ),-.                .-----------.
License: ...                 .-(           )-.      ╔══════|   LMS  Y  |══════╗
Content: ...                (    OER Cloud    )     ║      '-----------'      ║
Author: ...                  '-(           )-'  +-->║ Digital Systems 2021    ║
Versions: ...                   '-.(   ).-'     |   ║                         ║
                                     |          |
                                     +----------+          .-----------.
                                                |   ╔══════|  Webapp   |══════╗
                                                |   ║      '-----------'      ║
                                                +-->║ Digital Systems 2021    ║
                                                    ║                         ║

```
*Transformation of OER materials for use in various LMSs.*


### Features


###  Outlook

# Tutorial

## Extensions to Links

![Greek vase painting: seated young man writes on a wax tablet with a stylus](https://www.cvaonline.org/images/pottery/painters/keypieces/tiverios/21-p156bottom-medium.jpg "The so-called 'School cup' signed by the vase painter Douris. The seated man writes on a wax tablet with a stylus, showing the boy to the right how to do it. Early 5th c BCE. Berlin, Staatliche Museen.")

?[Sappho: Ode to Aphrodite](http://homoecumenicus.com/ioannidis_sappho_aphrodite.mp3 "Ancient Greek lyrical poem by Sappho (610-580BC). Original music by IOANNIDIS")

!?[Greek Art History from Goodbye-Art Academy](https://www.youtube.com/watch?v=Me0Psn6VrTg "_Black-Figure Dinos (Mixing Vessel); Warships (int.); Heroic Scenes (top)_, c. 520-515 BC. Circle of Antimenes Painter (Greek, Attic, active c. 530-510 BC). Veramic; diam. 50.8 cm; overall: 33.6 cm; rim diam. 34 cm. The Cleveland Museum of Art, Jon L. Severance Fund, 1971.46")

??[Neck Amphora](https://sketchfab.com/3d-models/197016-neck-amphora-0bb2525bdd734bf69d5a7b2b051928ad "_Neck Amphora_ (515-510 BC). Painter of Berlin 1899 (Greek). Greece, Attic, 6th Century BC Black-figure terracotta. Diameter: 29 cm (11 7/16 in.); Overall: 39.8 cm (15 11/16 in.). Andrew R. and Martha Holden Jennings Fund 1970.16 ")

??[Capacitor simulation by Falstad](https://www.falstad.com/circuit/circuitjs.html?startCircuit=cap.txt "A capacitor is a device that stores charge. As current flows into the capacitor, the voltage across the capacitor increases. As its voltage approaches the source voltage (the 5V voltage source shown on the left), the current flowing into the capacitor decreases.")

## Animation & Articulation


### 1. Animations


      {{1}}
> Animations in LiaScript are associated with double braces `{begin-end}`.

     {{2-4}}
| I  will              | begin at               |
| -------------------- | ---------------------- |
| animation-step **2** | and end at step **5**. |

      {{3}}
Inline animations work {4}{_similar_ ;-)}.

















### 2. Articulation

    --{{1}}--
Add an number in double braces to the head of a block let it appear at a
certain step.

      {{1}}
> Animations in LiaScript are associated with double braces `{begin-end}`.

     {{2-3}}
| I  will              | begin at               |
| -------------------- | ---------------------- |
| animation-step **2** | and end at step **3**. |


    --{{2}}--
Tables will be presented in more detail in the next part.

    --{{3}}--
Unpack the braces and define animations within a block.

      {{3}}
Inline animations work {4}{_similar_ ;-)}.


    --{{4 Russian Female}}--
«Для торжества зла достаточно бездействия хороших людей».


## Tables

### 1. Basics

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

### 2. Tables can be more

| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |             02 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |
| Sheep           |           90 |             12 |      95 |
| Human           |           68 |             70 |      10 |

### 3. Smart Visualization

| Music-Style 1994 | Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
|:---------------- | -------:| -------:| ------:| -------:| ---------:| -----:|
| Student rating   |      50 |      50 |    100 |     200 |       350 |   250 |


### 4. Combination with animations

<!-- data-transpose data-type="funnel" -->
| Music-Style {0-1}{1994} {1}{2014} |      Student rating |
|:--------------------------------- | -------------------:|
| Classic                           |   {0-1}{50} {1}{20} |
| Country                           |   {0-1}{50} {1}{30} |
| Reggae                            |                 100 |
| Hip-Hop                           | {0-1}{200} {1}{220} |
| Hard-Rock                         | {0-1}{350} {1}{400} |
| Samba                             | {0-1}{250} {1}{230} |

### 5. Customization

<!--
data-type="heatmap"
data-title="Seattle mean temperature in Fahrenheit"
data-ylabel="hours"
data-xlabel="month"
data-show
data-transpose
-->
| Seattle |  Jan |  Feb |  Mar |  Apr |  May |  Jun |  Jul |   Aug |  Sep |  Oct |  Nov |  Dec |
| -------:| ----:| ----:| ----:| ----:| ----:| ----:| ----:| -----:| ----:| ----:| ----:| ----:|
|       0 | 40.7 | 41.5 | 43.6 | 46.6 | 51.4 | 56.0 | 60.5 |  61.2 | 57.0 | 50.1 | 44.1 | 39.6 |
|       2 | 40.2 | 40.7 | 42.7 | 45.3 | 50.0 | 54.4 | 58.5 |  59.2 | 55.4 | 49.2 | 43.5 | 39.3 |
|       4 | 39.7 | 40.0 | 41.9 | 44.4 | 48.9 | 53.2 | 57.0 |  57.7 | 54.2 | 48.6 | 43.1 | 38.9 |
|       6 | 39.6 | 39.5 | 41.3 | 44.2 | 49.5 | 54.2 | 57.8 |  57.4 | 53.6 | 48.2 | 42.8 | 38.7 |
|       8 | 39.6 | 39.9 | 42.9 | 47.1 | 52.7 | 57.3 | 61.3 |  61.1 | 56.7 | 49.5 | 43.1 | 38.7 |
|      10 | 41.3 | 42.7 | 46.4 | 50.7 | 56.4 | 60.9 | 65.2 |  65.4 | 60.9 | 52.8 | 45.5 | 40.4 |
|      12 | 43.8 | 46.0 | 49.5 | 53.8 | 59.6 | 64.3 | 69.4 |  69.8 | 65.1 | 56.0 | 47.8 | 42.6 |
|      14 | 45.1 | 47.7 | 51.3 | 55.9 | 61.9 | 66.9 | 72.6 |  73.2 | 67.7 | 57.8 | 48.8 | 43.6 |
|      16 | 44.5 | 47.5 | 51.4 | 55.9 | 62.3 | 67.5 | 73.9 |  74.3 | 68.2 | 57.4 | 47.8 | 42.6 |
|      18 | 42.6 | 44.7 | 48.7 | 53.8 | 60.3 | 65.9 | 72.3 |  72.2 | 64.6 | 53.9 | 46.0 | 41.2 |
|      20 | 42.0 | 43.3 | 46.4 | 50.2 | 56.0 | 61.4 | 66.9 |  66.6 | 60.7 | 52.3 | 45.2 | 40.7 |
|      22 | 41.4 | 42.5 | 45.0 | 48.3 | 53.5 | 58.2 | 63.2 |  63.5 | 58.7 | 51.1 | 44.5 | 40.1 |


## ASCII-Art


### Type 1

                                    Multiline
    1.9 |
        |                 *
      y |               *   *
      - | r r r r r r r*r r r*r r r r r r r
      a |             *       *
      x |            *         *
      i | B B B B B * B B B B B * B B B B B
      s |         *               *
        | *  * *                     * *  *
     -1 +------------------------------------
        0              x-axis               1


### Type 2


```` ascii
                                       Peer A
                                       Server-Reflexive    +---------+
                                       Transport Address   |         |
                                       192.0.2.150:32102   o         |
                                           |              /|         |
                         TURN              |             /^|  Peer A |
   Client's              Server            |            / ||         |
   Host Transport        Transport         |           /  ||         |
   Address               Address           |      ____/   |+---------+
  10.1.1.2:49721       192.0.2.15:3478     |+-+  /      Peer A
           |               |               ||N| /       Host Transport
           |   +-+         |               ||A|/        Address
           |   | |         |               v|T|     192.168.100.2:49582
           |   | |         |               /+-+
.---------.|   | |         |o---------o   /              #---------#
|         ||   |N|         ||         | _/               |         |
| TURN    |v   | |         v| TURN    |/                 |         |
| Client  |----|A|----------| Server  #------------------|  Peer B |
|         |    | |^         |         |^                ^|         |
|         |    |T||         |         ||                ||         |
'---------'    | ||         o---------o|                |#---------#
               | ||                    |                |
               | ||                    |                |
               +-+|                    |                |
                  |                    |                |
                  |                    |                |
            Client's                   |            Peer B
            Server-Reflexive    Relayed             Transport
            Transport Address   Transport Address   Address
            192.0.2.1:7000      192.0.2.15:50000    192.0.2.210:49191
````

### Type LiaScript

---

```` ascii
😎                   👩

Bob                Alice
 |   "{1}{hello}"    |
 +------------------>|
 |                   |
 | "{2}{How r you?}" |
 |<- - - - - - - - - |
 |                   |
Bob                Alice

 😎                  👩
````

---

## Tasks

- [x] Task 1
- [ ] Task 2

## Quizzes

Can you define a quiz with less effort?

- [[ ]] Empty means not checked
- [[X]] Uppercase `X` means checked ...
- [[x]] ... and lowercase `x` too ...
- [[ ]] **as defined in the first line** ...

### More Quizzes


If $ I = \int (3x^{2}+125x+64) dx $, then what is $\int_{0}^{1} I dx$ equal to?

[( )] $\frac{159}{2}$
[( )] $\frac{171}{2}$
[( )] $\frac{221}{2}$
[(X)] $\frac{225}{2}$
[[?]] Integrate and apply the limits.
**************************************

__Consider__ $I = \int_{0}^{1} (3x^{2}+125x+64) dx$

Integrate

$$
I = \Bigg[ \frac{3x^2}{3} + \frac{125x^2}{2} + 64x \Bigg]_{0}^{1}
$$

==>

$$
   \Bigg( 3x^2 + \frac{125x^2}{2} + 64x \Bigg)_{0}^{1}
$$

==>

$$
   1 + \frac{125}{2} + 64
$$

==>

$$
   \therefore I = \frac{225}{2}
$$


**************************************

### German is weird

Guess the correct German article for:

[[male (der<!-- class="notranslate"-->)]   (female [die<!-- class="notranslate"-->])   [neuter (das<!-- class="notranslate"-->)]]
[    [X]           [ ]             [ ]     ]  Mann<!-- class="notranslate"--> - German for man
[    ( )           (X)             ( )     ]  Frau<!-- class="notranslate"--> - German for woman
[    [X]           [ ]             [ ]     ]  Junge<!-- class="notranslate"--> - German for boy
[    ( )           ( )             (X)     ]  Mädchen<!-- class="notranslate"--> - German for girl
[    [X]           [X]             [ ]     ]  Paprika<!-- class="notranslate"--> - German for bell pepper
[    (X)           (X)             (X)     ]  Joghurt<!-- class="notranslate"--> - German for yogurt


## Coding

``` js     -EvalScript.js
let who = data.first_name + " " + data.last_name;

if(data.online) {
  who + " is online"; }
else {
  who + " is NOT online"; }
```
``` json    +Data.json
{
  "first_name" :  "Sammy",
  "last_name"  :  "Shark",
  "online"     :  true
}
```
<script>
  // insert the JSON dataset into the local variable data
  let data = @input(1);

  // eval the script that uses this dataset
  eval(`@input(0)`);
</script>



> More examples at: https://github.com/topics/liascript-template

### What is Coding?


#### Math ...

``` text
(3 * x - 5x)^3 * (x + x)

60!
```
@Algebrite.eval


``` text
f=sin(t)^4-2*cos(t/2)^3*sin(t)

f=circexp(f)

defint(f,t,0,2*pi)
```
@Algebrite.eval

#### Music ...


``` abc
% autoplay: true

X: 1
T: Cooley's
M: 4/4
L: 1/8
K: Emin
|:D2|"Em"EBBA B2 EB|~B2 AB dBAG|"D"FDAD BDAD|FDAD dAFD|
"Em"EBBA B2 EB|B2 AB defg|"D"afe^c dBAF|"Em"DEFD E2:|
|:gf|"Em"eB B2 efge|eB B2 gedB|"D"A2 FA DAFA|A2 FA defg|
"Em"eB B2 eBgB|eB B2 defg|"D"afe^c dBAF|"Em"DEFD E2:|
```
@ABCJS.eval

> Template: https://github.com/LiaTemplates/ABCjs

#### Texts

``` text  Trump, Presidential Bid announcement
Thank you. It’s true, and these are the best and the
finest. When Mexico sends its people, they’re not sending
their best. They’re not sending you. They’re not sending
you. They’re sending people that have lots of problems, and
they’re bringing those problems with us. They’re bringing
drugs. They’re bringing crime. They’re rapists. And some,
I assume, are good people.

But I speak to border guards and they tell us what we’re
getting. And it only makes common sense. It only makes
common sense. They’re sending us not the right people.
```
@Textanalysis.FULL

> Template: https://github.com/liaTemplates/TextAnalysis



## How to create a LiaScript Macros
<!--
@bold: <span style="color: @0;">__@1__</span>


@license
> This file by @0 is made available under the Creative Commons CC0 1.0
> Universal Public Domain Dedication.
>
> The person who associated a work with this deed has dedicated the work to the
> public domain by waiving all of his or her rights to the work worldwide under
> copyright law, including all related and neighboring rights, to the extent
> allowed by law. You can copy, modify, distribute and perform the work, even
> for commercial purposes, all without asking permission.

@end

-->


@bold(#1290EE,@author)

---

@license(`@bold(#1290EE,@author)`)

## Scripting

The square of
<script input="range" default="0" output="x">@input</script>
is
<script>Math.sqrt(@input(`x`))</script>


### A bit more complex (CO2 offsetting by trees)

It can be concluded that the annual CO2 offsetting rate varies from
<script
input="range"
output="minCO2"
default="21.77"
format="number"
localeStyle="unit"
unit="kilogram" >
@input
</script>
$\frac{\text{CO}_2}{\text{tree}}$ to
<script
input="range"
output="maxCO2"
default="31.5"
format="number"
localeStyle="unit"
unit="kilogram" >
@input
</script>
$\frac{\text{CO}_2}{\text{tree}}$.
To compensate 1 tonne of CO2,
<script>
Math.round(1000 / @input(`maxCO2`))
</script>
to 
<script>
Math.round(1000 / @input(`minCO2`))
</script>
trees are needed.
In Europe, there are
<script
input="range"
output="minTrees"
default="300"
format="number" >
@input
</script>
to
<script
input="range"
output="maxTrees"
default="500"
format="number" >
@input
</script>
trees per hectare.
For calculating the figures on the Encon website, we assume a rate of 
<script
output="averageCO2"
format="number"
localeStyle="unit"
unit="kilogram" >
Math.round((@input(`minCO2`) + @input(`maxCO2`))/2, 2)
</script>
CO2/tree and an average of
<script
output="averageTrees"
format="number">
Math.round((@input(`minTrees`) + @input(`maxTrees`))/2, 2)
</script>
trees per hectare.
This means that 1 hectare of forest:
<script>@input(`averageTrees`)</script>
trees x
<script
format="number"
localeStyle="unit"
unit="kilogram">@input(`averageCO2`)</script>
$\frac{\text{CO}_2}{\text{tree}}$ =
<script
output="savings"
format="number"
localeStyle="unit"
unit="kilogram">@input(`averageTrees`) * @input(`averageCO2`)</script>
of $\text{CO}_2$ offsets, i.e.
<script format="number">@input(`savings`) / 1000</script> tonnes $\frac{\text{CO}_2}{\text{hectare}}$.


_Source:_ https://www.encon.be/en/calculation-co2-offsetting-trees

### Combining scripts with Markdown
<!--
sin: <script format="number"
             localeStyle="currency"
             currency="EUR"
             locale="de-DE"
             modify="false"
    > Math.sin(@input(`result`) + @input(`amp`) * @0) </script>
-->

Pos: <script run-once
        default="0"
        output="result"
        input="range" value="2" min="0" max="25" step="0.1"
        >
@input
</script>
and amplitude:
<script run-once
        default="0"
        output="amp"
        input="range" value="1" min="0" max="2" step="0.1"
        >
@input
</script>


<!-- data-type="barchart" -->
| Header 1 | <script>@input(`result`)</script> |
|:-------- |--------: |
| 1        | @sin(1)  |
| 2        | @sin(2)  |
| 3        | @sin(3)  |
| 4        | @sin(4)  |
| 5        | @sin(5)  |
| 6        | @sin(6)  |
| 7        | @sin(7)  |
| 8        | @sin(8)  |
| 9        | @sin(9)  |

### Scripts can output HTML and LiaScript too

The first value defines some kind of range:
<script input="range" value="2" output="range">@input</script>
, while the second can be interpreted as range
<script input="range" value="50" output="amplitude">@input</script>.
You can double-click on any gray element to inspect and edit its javascript code.


<script run-once style="display: inline-block; width: 100%">
function func(x) {
    x /= 10;
    return Math.sin(x) * Math.cos(x * @input(`range`) + 1) * Math.sin(x * 3 + 2) * @input(`amplitude`);
}

function generateData() {
    let data = [];
    for (let i = -200; i <= 200; i += 0.1) {
        data.push([i, func(i)]);
    }
    return data;
}

let option = {
    animation: false,
    grid: {
        top: 40,
        left: 50,
        right: 40,
        bottom: 50
    },
    xAxis: {
        name: 'x',
        minorTick: {
            show: true
        },
        splitLine: {
            lineStyle: {
                color: '#999'
            }
        },
        minorSplitLine: {
            show: true,
            lineStyle: {
                color: '#ddd'
            }
        }
    },
    yAxis: {
        name: 'y',
        min: -100,
        max: 100,
        minorTick: {
            show: true
        },
        splitLine: {
            lineStyle: {
                color: '#999'
            }
        },
        minorSplitLine: {
            show: true,
            lineStyle: {
                color: '#ddd'
            }
        }
    },
    dataZoom: [{
        show: true,
        type: 'inside',
        filterMode: 'none',
        xAxisIndex: [0],
        startValue: -20,
        endValue: 20
    }, {
        show: true,
        type: 'inside',
        filterMode: 'none',
        yAxisIndex: [0],
        startValue: -20,
        endValue: 20
    }],
    series: [
        {
            type: 'line',
            showSymbol: false,
            clip: true,
            data: generateData()
        }
    ]
}

"HTML: <lia-chart option='" + JSON.stringify(option) + "'></lia-chart>"
</script>

## How do you Share your content?

__Macros:__ https://github.com/topics/liascript-template

---

__Courses:__

`https://liascript.github.io/course/?YOUR-COURSE-URL`

https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/LiaScript_WeAreDevelopers2022/main/README.md
## Questions

Did you like the presentation so far?


    [(1)] no way, could not find a way out
    [(2)] not that bad actually
    [(3)] I don't care, was here to get faster to the lunch
    [(4)] was quite convincing
    [(5)] yes of course, LUA is the best ;-)

---

Will you use LiaScript in the future?

    [(yes)] Definitely, I will try it out
    [(maybe)] I am not sure at the moment
    [(no)]  No, I am not convinced

---

Which features will you use?

    [[TTS]]       The text-to-speech and animations
    [[Coding]]    The coding with the editor
    [[ASCII]]     The ASCII-art feature
    [[Tables]]    Tables to visualize data
    [[Quizzes]]   Interactive quizzes
    [[Scripting]] The JavaScript features and macros

## Additional resources

* __Project-Website:__ https://LiaScript.github.io
* __Open-Source:__ https://github.com/liascript
* __YouTube:__ https://www.youtube.com/channel/UCyiTe2GkW_u05HSdvUblGYg
* __Additional resources:__

  - Documentation: https://github.com/LiaScript/docs
  - Free books: https://github.com/LiaBooks
  - Templates: https://github.com/topics/liascript-template
  - Courses & ...: https://github.com/topics/liascript-course
  - Blog: https://aizac.herokuapp.com

* __Editor:__ https://code.visualstudio.com/Download

  - Liascript-Preview: https://marketplace.visualstudio.com/items?itemName=LiaScript.liascript-preview
  - Liascript-Snippets: https://marketplace.visualstudio.com/items?itemName=LiaScript.liascript-snippets

* __Development-Server:__ https://www.npmjs.com/package/@liascript/devserver

* __Exporter:__ https://www.npmjs.com/package/@liascript/exporter


---

How to contact us:

* via Twitter: https://twitter.com/LiaScript
* or via chat: https://gitter.im/LiaScript/community