# Opinionated File Structure For React Apps

<br/><br/>

## Two Things You Ought To Know First

**1. Opinionated -** The point of this guide is not to have to debate file structures with your team.

**2. Focus -** This guide does not focus on file structure best practices for React component libraries, although most of the practices mentioned here are applicable. Instead, it focuses on api-facing React apps that deal with data fetching, authentication, client and server states, etc

<br/><br/>

# Motivation

Looking two years back, I wish I'd known what exact file structure I should've gone with when I was just staring to build out a freshly POCed React app. It would've saved me so much time and effort. Instead, I had to wade through many file structure and naming refactors to get to the point the file structure of the same app is today.

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
