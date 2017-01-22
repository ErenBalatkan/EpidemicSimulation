# EpidemicSimulation
A Java Project made as an assignment of Advanced Object Oriented Programming course, project was graded 94 out of 100

## Simulation Rules

Scenario: The world is a NxN grid of countries. Each country may hold an unlimited number of people. A contagious virus is making people sick. When a person becomes sick, she looks unhealthy. When a person becomes infected, she does not immediately get sick, though, but enters a phase of incubation in which she is infectious (i.e. can transmit the virus to other people) but not sick (so she looks as if she is healthy). People infected with the virus (whether visibly or not) may transmit it to other people in the same country.

To avoid the virus, people travel across countries. They avoid countries that hold visibly sick people. Unfortunately, travelling people means the virus finds opportunity to spread to the whole world.

### Simulate the disease according to the following rules:

Each country, except those at the edge of the world, has 4 neighbors at the north, south, west, east side. Countries are connected to their neighboring countries. A person can travel from a country to a neighboring country. A direct travel from a country to another is otherwise not possible.

At the beginning, there are P people in the world. As an initial condition, X% of them are infected with the virus (but they are not sick yet). Initially people are assigned to countries uniformly at random.

After 6 days of becoming infected, a person becomes sick and is therefore visibly infectious (i.e. other people can understand that she is unhealthy).

After 14 days of becoming infected, a person dies with a probability of 25%. Dead people do not move, but stay visibly infectious.

After 16 days of becoming infected, a person becomes immune and is no longer visibly infectious, but remains infectious.

After 18 days of becoming infected, a person turns healthy. He is now in the same state as he was before his infection, which means that he can get infected again.

Each step of the simulation corresponds to one simulated day.

At the beginning of the simulation, each person decides when to move within the next 5 days. More precisely, she picks the moving day uniformly at random among the next 5 days. After moving, she repeats the same process. For example, if on day 0 the person decides to move after 3 days, she will move from her current country on day 3. After that move, she will make another decision: for example, she may decide to move after 5 days this time, so her next move will be on day 8, etc.

On the day of each move, a person will pick one of the countries available to her with equal probability and will move to it. The set of available countries is defined as the neighboring countries that contain no visibly infectious people. A person avoids countries with sick or dead (visibly infectious) people. This means that if a person is surrounded by visibly infectious people, she does not change position; however, she might change position the next time she tries to move (for example, if a visibly infectious person moved out of one of the neighbouring countries or became immune).

When a person moves into a country with an infectious person she might get infected according to the transmissibility rate of 40%, unless the person is already infected or immune. A person cannot get infected between moves (this is slightly unrealistic, but will simplify your implementation).

User Interface

The P, X, and N are parameters of the simulation. You must display the number of healthy, infected, sick, and dead people at the end of each day. These numbers should be displayed for each country, plus the whole world. You must implement the interface according to the MVC principle. If you’re working in pairs, you should have a graphical UI; otherwise, you may just have a command line interface.

### Extension Rules (That were added later, as an improvement to project after first rules were complete, for testing extensibility of the software)

The world is not flat anymore; it is round. That is, the countries in the upper edge of the grid are neighbours with those on the lower edge. Similarly, left edge countries are neighbours with the right edge countries.

There are genetically super people in the world (S% of the population, where S is taken as a parameter at the beginning of the simulation). These super people never get infected.

World Health Organization developed a vaccine. There are doctors (D% of the population; taken as a parameter at the beginning of the simulation) that can apply the vaccine. A doctor can vaccinate at most V people (V is a parameter) each day. A Doctor can vaccinate people that are in the same country with the doctor. Only healthy people are vaccinated. Once vaccinated, a person becomes immune for life.

There is air traffic. When a person decides to travel, with A% probability (A is a parameter), she chooses to use air travel to fly to a random country (countries with visibly-infected people are NOT avoided).

## Credits 
Eren Balatkan - e.balatkan@gmail.com

İrem Toru - toruirem@gmail.com

M. Uluç Şahin - ulucsahin@gmail.com
