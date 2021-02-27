# Project 3 Milestone
### Basic Approach
For this project, I used the approach laid out in the "Implementing Your Router" section of the project description, completing the first 4 steps. After studying the test config files and reviewing the starter code, this involved writing logic to handle `update`, `data`, and `dump` messages from servers.

For `update` packets, I modified the routing table (internally represented as a dictionary) to include the new route. I then sent my own `update` messages to all adjacent servers except the one that initially sent me the `update` message.

For `data` packets, I simply forwarded the recieved packet to the correct server.

For `dump` packets, I modified the `dump` packet to become a `table` packet instead, and then sent the modified packet to the server that requested it.

### Challenges
The main challenges I encountered were related to IP address manipulation. It was frustrating to have to constantly think about how I needed to modify IP addresses in each function, so I eventually opted to make an `IPUtils` class that contained a number of utility functions for manipulating IP addresses. This ended up being extremely helpful. It currently includes 3 methods, only 2 of which are in use, but it will be expanded significantly for the final product.

### Testing
I performed all of my testing using the provided simulator. Because the simulator only outputs messages about *what* is incorrect rather than *how* it is incorrect, I opted to add numerous print statements throughout my code for debugging purposes. This helped me to see exactly what my code was doing and why this was causing my program to crash or the simulator to reject input.