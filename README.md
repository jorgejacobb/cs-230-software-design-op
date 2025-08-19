# cs-230-software-design-op
CS 230 portfolio repo – Software Design doc + Module 8 journal
Jorge Fernando Moreno Jacob
Southern New Hampshire University 
August 19, 2025 

## 1) Client & Requirements
**Client:** The Gaming Room (TGR)  
**Project:** Take Draw It or Lose It from an Android app to a web app that runs on many platforms.  
**Main needs:** A small server with a REST API, secure login with roles, lots of concurrent players/teams, and a browser UI that works on desktop and mobile. We also need a basic plan for storing images/data and keeping memory use reasonable.

---

## 2) What I did well
I split the problem into clear parts (server, client, storage, security, deploy).  
I picked one simple, consistent approach (client–server with REST/JSON) and explained why.  
For the demo I kept auth basic so it’s easy to run, but I noted how we can upgrade it later.  
Overall, I tried to keep the document short and easy to follow.

---

## 3) Helpful parts of the design process
Filling out the design doc forced me to turn vague goals (“support many players”) into real choices: stateless endpoints, a small image cache, optional CDN, and health checks.  
The OS comparison table helped me choose a primary server OS with reasons.  
Listing the REST endpoints made it clear what the prototype actually has to do first.

---

## 4) What I would revise and how
Next pass, I’d replace Basic Auth with JWT/OAuth, add simple rate-limiting, and tighten input validation.  
I’d include a tiny cost sketch (1 cloud VM + object storage + bandwidth).  
I’d also add a basic CI workflow (lint/tests) and do a quick load/latency check so we see real numbers.

---

## 5) Interpreting user needs in the design
Players want to jump in fast with no installs, so the client is just a web page talking JSON to the API.  
To keep things snappy, images are streamed and cached (not all preloaded).  
Static stuff (images) is stored separately from changing data (players/scores), which makes backups and scaling easier.

---

## 6) How I approach designing software (now and in the future)
I start with a few user stories and constraints, sketch a simple diagram, then build the smallest useful slice.  
I like API-first design, early tests, and measuring performance instead of guessing.  
Security isn’t an afterthought—I try to add the basics early and level it up as the project grows.
