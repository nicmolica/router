Nicholas Molica (nicmolica), March 2021

# Router Control System Implementation
This is a from-scratch implementation of the control system for a router. It is meant to function exactly the same as an actual router does, but in a simulated environment. The control system takes care of routing packets, maintaining a forwarding table (including coalescing and decoalescing entries), filtering out invalid requests, and all the other functions a router would normally perform.

## Technology Used
This project is implemented in Python and uses the `json` and `socket` modules, as well as other general purpose modules. No routing logic modules are used, as the purpose of this project was to practice writing the algorithms necesary for industry-quality routing from scratch. Unfortunately, I'm no longer able to run the simulator because I lost access to it after March, but if asked, I can provide a code walkthrough.

## Development Process
In order to make the code in this project easy to understand, I wrote it in an object oriented style. The factory design pattern is very prominent in the code, as the process of deciding which forwarding route to use involves many filtering steps. I felt that this would be easiest to do using the factory pattern, whittling down the possibilities until there was only one left. Because this was such an extensive project, I also wanted to approach development with an organized approach. I started by mapping out the order in which I would design the functionality, to avoid the pitfalls of either trying to do too much at once, or writing code that was only testable in integration. To remedy this, I organized the route filtering into several key pieces of functionality, and implemented them one at a time. Apart than this filtering algorithm, the rest of the project was trivially simple and involved simple socket functionality and if-else logic.
