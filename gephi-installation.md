# Gephi installation

Gephi is a tricky software. It is basically an Abandonware: 0.9.2 version was released on September 24, 2017. It still mostly works, but problems with running it accumulate over time. We always don't know which issues we will encounter this time, so be ready for anything!

**Why use it, then?** Despite the weird situtation with its maintainers, Gephi is very powerful both for beginner-level and advanced work with networks: deep customization options, great for tinkering with visualizations. It is almost impossible to replace it in the teaching context. That said, if you are serious about network analysis and a dedicated R user, it may be worth to look past Gephi and have all control in your hands. There are some great libraries and tutorials for working with networks inside your R (some links are provided in the end of this note)

## 1. Download

Download page:
https://gephi.org/users/download/

So far, so good! Choose the Gephi downloadable for your system (Mac, Linux, Windows) and hope for the best!

**Be sure to check installation instructions:**
https://gephi.org/users/install/

## 2. Java

Gephi runs on Java, but only on older ones, so you will need a version 8 of it. *Gephi does not run with latest versions of Java > 8*.

If you are not sure how to install Java, follow "Instructions" guide near to download links on the Java site.

https://java.com/en/download/

**NB**. For Linux users: Java JRE 8 didn't seem to work for on my latest system (Linux Mint 20). If it is the same for you, should be fixable by installing Open JDK 8:

`sudo apt-get install openjdk-8-jdk`

Then switching the system to this new from running

`sudo update-alternatives --config java`

Just pick a JDK 8 Java from the list


## 3. Gephi. First boot

Run gephi.exe (Windows), ./bin/gephi script (Linux), or Gephi app. Does it work? If yes, you'll probably see a loading screen and, after that, an interface asking you what you want to do. Something like that:

![](https://i.imgur.com/iVw5wq0.png)

You are lucky if you see this screen! If not, however... see **Troubleshooting**

## 4. Gephi. Getting started

We will show you how to build some Gephi graphs during the workshop, but there are also many others great places to learn. I especially like the [tutorial from Clément Levallois for its clarity](https://seinecle.github.io/gephi-tutorials/generated-html/simple-project-from-a-to-z-en.html).


A whole section of tutorials is on the Gephi's main site:
https://gephi.org/users/



## Troubleshooting

Most probably, your problem comes from the wrong Java version. On each system, manipulating Java instances can be tricky. Googling may be profitable, also check this forum thread.

http://forum-gephi.org/viewtopic.php?t=6296

General way to deal with "unknown" path to proper Java instance, is manually setting the path in the Gephi config file: `gephi-0.9.2/etc/gephi.conf` 

You should see a commented line there with `jdkhome` path:

``#jdkhome="path/to/java"``

Change the quoted path to your Java 8 instance AND uncomment the line (remove # sign), e.g.:

`jdkhome="C:\Program Files (x86)\Java\jre1.8.0_144"`

Feel free to discuss your encountered issues and technical difficulties in Discord, so everyone can tune in.

### Opens interface, but does not render a graph in the "Overview"

If you encounter this, probably you are on Linux. Try running 

## Network analysis in R

If you are feeling like doing everything in R, there are many great options to learn network analysis and viz within this language environment. Dynamic networks, animated networks, html-based networks that can be easily embedded into web - you name it!

A comprehensive tutorial with many additional links to sources and research by **Katherine Ognyanova**, Rutgers University:

**[Static and dynamic network visualization with R](https://kateto.net/network-visualization)** (2019)

You can also explore [``ggnet2`` ](https://briatte.github.io/ggnet/)library for R that builds directly on top of `ggplot2` syntax and consice grammar of graphics:


`install.packages("networkD3")`  

`library(stylo)`
`stylo.network()`
