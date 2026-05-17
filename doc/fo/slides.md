---
theme: seriph
# background: https://cover.sli.dev
title: One Command to Find the Most Vulnerable Python Package on Your System
class: text-center
transition: slide-left
comark: true
---

# One Command to Find the Most Vulnerable Python Package on Your System

Christopher Ariza <br/>
CTO, Research Affiliates




---
layout: center
class: text-center quote
---

<style scoped>
.slidev-layout {
  background-color: #0f0f1e;
  background-image: radial-gradient(ellipse 60% 50% at 50% 50%, rgba(60, 60, 110, 0.5) 0%, transparent 100%);
}
</style>

```sh
uvx fetter audit --cvss
```




---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>


Security of the Python Ecosystem


<!--
I am concerned about the security of the Python ecosystem, and you should be too
 -->


---
class: history
---

# Countless Stories of Compromised Packages

<div class="relative w-full h-90 mt-4">
  <img v-click src="/supplychain/image0.png" class="absolute w-45 shadow-xl" style="top: 5%; left: 5%; transform: rotate(-3deg);" />
  <img v-click src="/supplychain/image1.png" class="absolute w-45 shadow-xl" style="top: 8%; left: 15%; transform: rotate(2deg);" />
  <img v-click src="/supplychain/image2.png" class="absolute w-45 shadow-xl" style="top: 3%; left: 25%; transform: rotate(-5deg);" />
  <img v-click src="/supplychain/image3.png" class="absolute w-45 shadow-xl" style="top: 10%; left: 35%; transform: rotate(4deg);" />
  <img v-click src="/supplychain/image4.png" class="absolute w-45 shadow-xl" style="top: 6%; left: 45%; transform: rotate(-2deg);" />
  <!-- <img v-click src="/supplychain/image5.png" class="absolute w-45 shadow-xl" style="top: 2%; left: 35%; transform: rotate(6deg);" /> -->
  <img v-click src="/supplychain/image6.png" class="absolute w-45 shadow-xl" style="top: 12%; left: 55%; transform: rotate(5deg);" />
  <img v-click src="/supplychain/image7.png" class="absolute w-45 shadow-xl" style="top: 4%; left: 65%; transform: rotate(-2deg);" />
  <img v-click src="/supplychain/image9.png" class="absolute w-45 shadow-xl" style="top: 7%; left: 35%; transform: rotate(5deg);" />
</div>


<!--
Countless stories of compromised packages delivering malware should keep you up at night
 -->




---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>


A tool to find packages with vulnerabilities


<!--
My concern led me to create a tool to find all the packages on your system and determine if they have vulnerabilities
 -->




---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>


`fetter`

<!--
This tool is called fetter, and course, it is written in fast, multi-threaded Rust
 -->




---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>


Finds *all* the packages



<!--
Now, fetter finds all the packages, not just those declared in your requirements files. It finds those abandoned virtual environments and projects you forgot about, or those system-installed packages you did not know where there
 -->


---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>

Broad functionality

<v-clicks>

Enforce allow lists

Monitor organization-wide package exposure

Find the most vulnerable package on a system
</v-clicks>


<!--
We can do a lot with that information...

 -->







---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>


How dow we measure most vulnerable?

<!--
Now you might be wondering how we determine what is the most vulnerable?
 -->



---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>


Common Vulnerability Scoring System (CVSS)

<!--
We have a system for measuring vulnerability severity called CVSS. It scores vulnerabilities on a scale from 1 to 10.
 -->



---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>

CVSS Sources

<v-clicks>

NIST National Vulnerability Database

Open-Source Vulnerability Database
</v-clicks>

<!--
Fortunately, we have the NIST NVD and the Open-Source Vulnerability Database that make finding those CVSS scores easy
 -->




---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>

Steps

<v-clicks>

Find all Pythons

Find all site packages directories

Look up all packages in the OSV

Find the highest CVSS scores

One command

</v-clicks>


<!--
 -->






---
layout: center
class: text-center quote
---

<style scoped>
.slidev-layout {
  background-color: #0f0f1e;
  background-image: radial-gradient(ellipse 60% 50% at 50% 50%, rgba(60, 60, 110, 0.5) 0%, transparent 100%);
}
</style>

```sh
uvx fetter audit --cvss
```


---
layout: center
class: text-center quote
---

<style scoped>
.slidev-layout {
  background-color: #0f0f1e;
  background-image: radial-gradient(ellipse 60% 50% at 50% 50%, rgba(60, 60, 110, 0.5) 0%, transparent 100%);
}
</style>

```sh
uvx fetter audit --cvss=9.4
```



---
layout: center
class: text-center quote
---

<style scoped>
.slidev-layout {
  background-color: #0f0f1e;
  background-image: radial-gradient(ellipse 60% 50% at 50% 50%, rgba(60, 60, 110, 0.5) 0%, transparent 100%);
}
</style>

```sh
uvx fetter search -p torch-2.3.1

```


---
layout: center
class: text-center quote
---

<style scoped>
.slidev-layout {
  background-color: #0f0f1e;
  background-image: radial-gradient(ellipse 60% 50% at 50% 50%, rgba(60, 60, 110, 0.5) 0%, transparent 100%);
}
</style>

```sh
uvx fetter purge-pattern -p torch-2.3.1
```




---
layout: center
class: text-center
---

<style scoped>
.slidev-layout {
  background-color: #111122;
}
</style>

```sh
pip install fetter
```






---
layout: center
class: text-center
---

# Thank You

https://flexatone.net

<!-- <PoweredBySlidev mt-10 /> -->
