In this section, we'll explore network analysis as a tool for understanding relationships between people and things.

[TOC]

## What is network analysis? 

Networks are everywhere. Once you start, it's hard to stop seeing them. The internet is a network, Facebook is a network, [Kevin Bacon](https://oracleofbacon.org/) is the central node in the Hollywood network. Studying the connections between people and things is a major activity in the humanities, so "network analysis" feels like a natural method for working with humanities data. Network analysis varies by discipline, but originates from graph theory in mathematics. This is a simplification, but the idea is that one can measure significant people in a network by how many connections they have to other people and by the weight or significance of those connections. You can also learn who might serve as a bridge between social groups or whether you have a dense network of highly connected people or a more disperse group. We can visualize these networks through a network graph - points connected by lines. 


You don't necessarily have to just study people with network analysis, but it's a common approach. The specific name for this methodology is **SNA** or Social Network Analysis. SNA is used in many disciplines, with a heavy presence in the social sciences. It's important to recognize that each discipline will have its own conventions and expectations for SNA. You should tread carefully until you have a firm foundation. As Scott Weingart reminds us in "[Networks Demystified](http://www.scottbot.net/HIAL/index.html@p=6279.html):" 

> "Networks can be used on any project. Networks should be used on far fewer."

This is not to scare you! But learning about network analysis is the perfect moment to pause and remember that you are not working in a vacuum. The methods you use have a historical and modern context and you are responsible for learning that context. 

That being said, network visualizations can be a great place to start. They can help you learn more about your data or illuminate a new direction for your research agenda. Plus, they're fun. Learning the basics will help you be better judge of whether it is, in fact, a good fit for your project. 


## Nodes, edges, ties, what?
Let's take a moment to define some of the terms you'll encounter in network analysis. 

* Nodes/points/agents/vertices - All of these words refer to the points on your network graph. 

* Edges/ties - Refers to the connections between nodes. Edges can be weighted (stronger or weaker edges) or directional (some relationships are mutual, some are not).

* Centrality - the more connections a node has, the more central they are to the network. You can measure centrality in different ways, such as betweenness (the shortest distance between nodes) or eigenvector (way to measure influence in a network).

* Attributes - Information about your nodes. If your network contains people, attributes might be their age, birth dates, affiliation, occupation, etc. 

* Bimodal or multi-modal - a network in which more than one type of thing is being connected. Authors to their books, or people to places. 

## Network data 
To visualize your network, you need to set up your data is particular way. This might vary depending on the software you use, but it's a good place to start: 

An **edge list** is a two-column spreadsheet that forms the the network by listing the nodes and their connections. It's in a deceptively simple format:

|Source|Target|
|---|---|
|Kevin Bacon|John Lithgow|
|Kevin Bacon|Sarah Jessica Parker|
|Sarah Jessica Parker|Matthew Broderick|
|Matthew Broderick|Jennifer Grey|
|Jennifer Grey|Patrick Swayze|
|Patrick Swayze|Demi Moore|
|Demi Moore|Kevin Bacon|
|Jennifer Grey|Laurence Fishburne|
|Laurence Fishburne|Keanu Reeves|
|Kevin Bacon|Laurence Fishburne|

You'll notice that some names can appear more than once, and not necessarily in the same column. Each of these rows represents a single connection, in this case, a movie. Take a minute to try to draw this extremely limited 80s-90s movie network on paper. What do you expect to see? Who has the most connections? Who seems central and who seems like an outlier? How flawed is this network? Add to it if you can. 

An edge list might build the network, but we need an **attribute table** to add context to our network. An attribute table lists each node only once, then displays information about that node in subsequent columns. 

|Name|Gender|Is known for a dance scene|
|---|---|---|
|Kevin Bacon|M|Y|
|Matthew Broderick|M|Y|
|Laurence Fishburne|M|N|
|Jennifer Grey|F|Y|
|John Lithgow|M|N|
|Demi Moore|F|Y|
|Sarah Jessica Parker|F|N|
|Keanu Reeves|M|N|
|Patrick Swawyze|M|Y|

Now I can use this information to filter or slice the view of my network. I can also use it to refine my questions or my data set. It's easy for me to see that I have [more men in my network](https://6dfb.tumblr.com/post/44879380376/an-entry-of-ones-own-or-why-are-there-so-few) than women.

If you want to see this data as a visualization, try loading it into [Palladio](http://hdlab.stanford.edu/palladio-app/#/upload).

Copy and paste the following text into the white box in Palladio, then press `Load`: 

```
Source,Target,
Kevin Bacon,John Lithgow,
Kevin Bacon,Sarah Jessica Parker,
Sarah Jessica Parker,Matthew Broderick,
Matthew Broderick,Jennifer Grey,
Jennifer Grey,Patrick Swayze,
Patrick Swayze,Demi Moore,
Demi Moore,Kevin Bacon,
Jennifer Grey, Laurence Fishburne,
Laurence Fishburne, Keanu Reeves,
Kevin Bacon, Laurence Fishburne,
```
To generate a network, visit the `Graph` tab. Use the menu on the right of the screen to select the "source" column in `Source` and the "target" column in `Target`. You should see a network appear! Does it look like what you expected? 


## PageRank and Graph Databases 

## Tools 

* [Palladio](http://hdlab.stanford.edu/palladio/) is a data visualization tool created by Stanford's Humanities + Design Research Lab. It's a browser-based tool that accepts structured data and creates network, geospatial, and gallery visualizations. It's easy to use, but can crash under too much data. It's a great way to create first draft visualizations of your data. 

* [Gephi](https://gephi.org/) is a robust network/graph visualization tool. It runs from your computer and can accept large data sets (though you will need some patience). Gephi has a lot of options for changing the appearance of your network via filters and layout. You can also generate statistics about graph density etc. There are a number of [tutorials](https://gephi.org/users/) available.

* 


## Activities

### Activity 1 
Network by had 

### Activity 2


## Resources


## Readings
* [Demystifying Networks](http://www.scottbot.net/HIAL/index.html@p=6279.html)