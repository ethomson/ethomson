# My GitHub contributions as a Game of Life

[![GitHub Game of Life](https://github4life.herokuapp.com/ethomson.gif?z=6)](https://github4life.herokuapp.com/ethomson)

(Be sure to click on it for the infinite scrolling version.)

### What's this?

This takes my GitHub contribution graph and uses it as the initial state for [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life), a popular cellular automaton that is often built by beginning software developers as an easy-to-implement but interesting piece of software.

Conway's Game of Life only defines two initial states for cells, but there are [multi-color variants](https://conwaylife.com/ref/mniemiec/color.htm).  This is a variant of "Quad Life" (chosen because the GitHub contribution graph has four colors that represent the intensity of contributions for a given day): in the typical Game of Life rules, a graph with a lot of contribution would die out in the first iteration (because the cells would be overcrowded), which seems to punish those with a lot of contributions, giving them a boring Game of Life.  Intead, this variant "decays" the level of contribution, so cells will fade away instead of dying immediately.

### How does it work?

This uses a JavaScript library called [contributions](https://npmjs.com/contributions) to create a data structure with a GitHub contribution graph, and uses that as the initial state for another JavaScript library called [dat-life](http://npmjs.com/dat-life).

A simple Node.js application called [github4life](https://github.com/ethomson/github4life) -- so named because it takes a _GitHub_ contribution graph and turns it into a _4_ color Game of _Life_ -- renders this as an animated GIF.  When talking to GitHub's image caching service (camo) it will render 20 frames and then stop (so that the resulting image can actually be cached) but when you hit it with your web browser, it will render the game of life on-demand - infinitely continuing to deliver you the next state as a new frame in the GIF, forever.

