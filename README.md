# Opinionated File Structure For React Apps

<br/><br/>

## Two Things You Ought To Know First

**1. Opinionated -** The point of this guide is not to have to debate file structures with your team. Since there is no "right" file structure like there is no "right" code formatting style, there is always going to be debates what file structure works best. For that reason the goal of this guide is to eliminate any potential debates when it comes to file structures. Similarly how Prettier with its default configuration is meant to elimiinate any potential code formatting style debates.

**2. Focus -** This guide does not focus on file structure of React component libraries, although most of the practices mentioned here are applicable. Instead, it focuses on API-facing CRUD (Create, Read, Update, Delete) React apps that deal with data fetching, authentication, client and server states, etc.

<br/><br/>

# Motivation
Knowing what exact file structure and naming convention to adopt right out the the gate can save you and your team a lot of time and effort. Not knowing this could have you wade through many different refactors until you get to the structure that feels right for you and your team.

What I mean by "feels right" is that there is no right file strucutre. Every team and every project is in a certain way different. That means that each team should pick a file structure that works for them.
[React official docs](https://reactjs.org/docs/faq-structure.html) tells you not to think about file structure too much and to figure it out as the app grows. In my experience, unfortunately this approach did not work out well and for that reason I'd like to share the knowledge I gained during this time. 

<br/><br/>

# The Problem

**1. File structure -** you want to know what your file structure will look like right from the get-go. You want a time-proof file structure that will scale well without having to refactor eventually. You googled it up and read dozens of articles. You found most of them vague without explaining too much if at all, what the exact benefits of a specific file structures are.

**2. Refactors due to app growth -** you want to avoid any potential refactors due to application growth over time. More often than not, api facing React apps are heavily form oriented. Such apps can grow very fast and very wide. Not thinking too much about file structure from the get-go can lead to refactors
even before you know it due to fast growing nature of these type of apps.

**3. Naming -** you want to know what naming convetions files and folders will have from day one. At the start, names can be very generic without any repercussions however as the app grows, names have to be more and more specific with more context included in the names per sei. In order to avoid having to rename, it's a good idea to adopt a convetion that will still have legs even two years from the boostrapping.

<br/><br/>

# This Solution

<br/><br/>
