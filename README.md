<!--

author:   André Dietrich, Sebastian Zug
email:    andre.dietrich@informatik.tu-freiberg.de & sebastian.zug@informatik.tu-freiberg.de
version:  0.0.1
language: de
narrator: Deutsch Female

import:   https://raw.githubusercontent.com/liascript-templates/plantUML/master/README.md
          https://raw.githubusercontent.com/liascript-templates/plantUML/master/README.md
          https://raw.githubusercontent.com/liaTemplates/AVR8js/main/README.md
-->

# LiaScript - Interactive Markdown for Education & Documentation

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/LiaPlayground/LiaScript_WeAreDevelopers2022/master/README.md#1)

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
