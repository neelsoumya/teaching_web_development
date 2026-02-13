# Bonus Material: History of Web Development

## History of web development

- [Video Lecture on the History of Web Development](https://youtu.be/6kRMlfIBMCY?si=u-riHVr0KNqGCisx)

## Early Days

The history of web development dates back to the early 1990s when Tim Berners-Lee invented the World Wide Web. The first website went live in 1991, and it was a simple page with text and hyperlinks. Early web development primarily involved creating static HTML pages.

### Data problem

In the late 1980s, CERN (the European Organization for Nuclear Research) wasn't just smashing particles; it was drowning in a digital "Babel." The problem wasn't just the sheer volume of experimental data—it was the **fragmentation** of that information.

![Data problem](../images/birth_web_data_problem.png)


Here is the breakdown of the crisis that birthed the modern internet.

---

### 1. The "Information Babel"

Physicists from all over the world came to CERN to work on experiments, but they all brought their own computers, software, and file formats.

* **Incompatibility:** Data stored on a VAX computer couldn't easily be read by a Unix workstation.
* **High Turnover:** Researchers would finish their stints and leave, taking the "institutional memory" of how their data was organized with them.
* **The Search Crisis:** If you needed a specific technical manual or a result from a previous experiment, you had to find the right person, on the right floor, who happened to have the right diskette.

### 2. The Tipping Point: Complexity

By 1989, CERN was the largest internet node in Europe, but the internet back then was like a library without a card catalog. You could send a file (via FTP) or log into a remote computer (via Telnet), but you had to know exactly **where** the information was located before you could go get it.

As the Large Electron-Positron collider (LEP) began generating massive amounts of data, the manual "detective work" required to find documentation became a significant bottleneck for scientific progress.

### 3. The Proposal: "Vague but Exciting"

In March 1989, a British software consultant named **Tim Berners-Lee** wrote a proposal titled *"Information Management: A Proposal."* His boss, Mike Sendall, famously scribbled **"Vague but exciting..."** on the cover.

Berners-Lee’s genius was realizing that the information didn't need to be moved into one giant database. Instead, it could stay where it was, but be **linked** together using **hypertext**.

### 4. How Hypertext Solved the Problem

To fix CERN's chaos, Berners-Lee developed three fundamental technologies that we still use every second today:

* **HTML (HyperText Markup Language):** A universal "language" for documents.
* **HTTP (HyperText Transfer Protocol):** A way for computers to ask for and send those documents.
* **URL (Uniform Resource Locator):** A unique "address" for every piece of information.

> **Fun Fact:** The very first web server was a NeXT computer at CERN. It had a hand-written label in red ink that read: *"This machine is a server. DO NOT POWER IT DOWN!!"*

---

By creating a system where a document on one computer could link to a document on another—regardless of the hardware—Berners-Lee turned a chaotic mess of data into a "web" of knowledge.


## Early pioneers

- 🛠️ [Diagram by Tim Bernes Lee at CERN](https://www.w3.org/History/1989/proposal.html)
- Original WWW architecture diagram!

- [Original NEXT computer used to design Web](https://artsandculture.google.com/asset/original-next-computer-used-by-sir-tim-berners-lee-to-design-the-world-wide-web-next/6QHcxbuGnQ4rng?hl=en)

- Mike Sendall commented `vague but exciting ...`
- [scan of paper](https://info.cern.ch/Proposal.html)

- Mike Sendall was Tim Berners‑Lee’s boss at CERN and played a quiet but crucial enabling role in the birth of the World Wide Web

- With Sendall’s backing, prototype software for a basic web system was working by the end of 1989 and then refined by Berners‑Lee and Robert Cailliau in 1990

- In the late 1980s Robert Cailliau proposed an internal hypertext system at CERN for managing documentation, anticipating many of the ideas that would soon become central to the Web. When Tim Berners‑Lee proposed the World Wide Web in 1989–1990, Cailliau collaborated closely with him, co‑authoring funding proposals and strongly advocating for the project within CERN


If CERN’s invention of the Web was about creating a "library" of information, **ARPANET** was the project that built the "roads" and "pipes" that allow that information to travel.


## ARPANET

While the Web (HTML, HTTP) was born in 1989, the **ARPANET** (Advanced Research Projects Agency Network) began two decades earlier in **1969**. It was the world's first successful "network of networks."

---

### 1. The Core Purpose: Resilience & Resource Sharing

In the late 1960s, the U.S. Department of Defense (ARPA) had two major problems:

* **The Resource Problem:** Computers were massive, expensive mainframes. Researchers at one university couldn't easily use a specialized computer at another without physically traveling there.
* **The Survival Problem:** During the Cold War, the military feared that a single strike on a central "hub" could take out the entire nation's communications. They needed a decentralized system.

### 2. The Technological Breakthrough: Packet Switching

Before ARPANET, communications used "circuit switching" (like old phone lines). If the line broke, the call died. ARPANET introduced **Packet Switching**:

* Information is broken into small "packets."
* Each packet finds its own path to the destination.
* If one node is destroyed or busy, the packets automatically reroute through another path.
* The packets are reassembled at the end.

### 3. The First Four Nodes (1969)

The first version of the internet consisted of only four computers at four western U.S. universities:

1. **UCLA** (University of California, Los Angeles)
2. **SRI** (Stanford Research Institute)
3. **UCSB** (University of California, Santa Barbara)
4. **University of Utah**

> **The First "Crash":** On October 29, 1969, researchers tried to send the word **"LOGIN"** from UCLA to SRI. The system crashed after the first two letters. Thus, the first message ever sent on the internet was simply: **"LO"**.

### 4. Key Milestones: From Network to Internet

ARPANET wasn't the internet yet; it was a single network. Two major things happened to turn it into the global "Internet":

* **The Invention of Email (1971):** Ray Tomlinson chose the **@** symbol to separate a user's name from their computer's name. It became the first "killer app."
* **TCP/IP (January 1, 1983):** Known as "Flag Day," this was when ARPANET switched to the **Transmission Control Protocol / Internet Protocol**. This allowed different types of networks to talk to each other, effectively creating the "Inter-network" (Internet).

---

### The Big Picture: How They Connect

To help your students distinguish the two, you can use this analogy:

| Feature | ARPANET / The Internet | The World Wide Web (CERN) |
| --- | --- | --- |
| **Analogy** | The **Tracks and Engines** | The **Cargo and Passengers** |
| **Function** | How data moves from point A to B. | How that data is formatted and linked. |
| **Language** | TCP/IP | HTML / HTTP |
| **Era** | 1969 (The "Plumbing") | 1989 (The "Interface") |


## Evolution of Technologies

As the web grew in popularity, new technologies emerged to enhance web development. In the mid-1990s, JavaScript was introduced, allowing developers to create interactive elements on web pages. The late 1990s saw the rise of server-side scripting languages like PHP and ASP, enabling dynamic content generation.

## Apache history

The Apache HTTP Server, commonly referred to as Apache, is one of the most popular web server software applications in the world. It was created by a group of developers known as the Apache Group in 1995. 

Apache played a significant role in the growth of the World Wide Web by providing a reliable and open-source platform for hosting websites. Over the years, Apache has undergone numerous updates and improvements, making it a robust and flexible choice for web developers.

## Modern Web Development

In the 2000s, web development saw the rise of frameworks and libraries that simplified the development process. Technologies like AJAX allowed for asynchronous data loading, leading to more dynamic and responsive web applications. The introduction of HTML5 and CSS3 further enhanced the capabilities of web development, enabling richer multimedia experiences.

## Frameworks

The 2010s witnessed the emergence of various web development frameworks such as Angular, React, and Vue.js for front-end development, and Node.js, Django, and Ruby on Rails for back-end development. 

These frameworks provided developers with tools and structures to build complex web applications more efficiently.

HTML was created by Tim Berners-Lee in 1991 as a way to share documents over the internet. Since then, it has evolved through various versions, with HTML5 being the latest standard, introducing new elements and APIs for modern web development.

- Next browser from CERN: [CERN Next Browser](https://next.cern.ch/)

The Next browser was one of the earliest web browsers developed at CERN, where Tim Berners-Lee worked. It played a crucial role in the initial adoption of the World Wide Web.

- NCSA Mosaic: [NCSA Mosaic](https://en.wikipedia.org/wiki/NCSA_Mosaic)

NCSA Mosaic was one of the first web browsers to gain widespread popularity, significantly contributing to the growth of the World Wide Web in the early 1990s.

Here is an image of the NCSA Mosaic browser (created using an AI image generator):

![Image of NCSA Mosaic browser](../images/ncsa_mosaic.png)

- Wayback Machine: [Wayback Machine](https://archive.org/web/)

The Wayback Machine is a digital archive of the World Wide Web, allowing users to access and view historical versions of web pages. It serves as a valuable resource for understanding the evolution of web design and content over time.

For example, here is what the Yahoo homepage looked like in 1996: [Yahoo 1996](https://web.archive.org/web/19961220154510/https://www.yahoo.com/)



## References

- [The Apache Software Foundation](https://www.apache.org/): A history of the Apache HTTP Server and its impact on web development.


- [Next: HTTP basics](http.md)