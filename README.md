# Data Visualization Project

## Visualizing Main Characters of Game of Thrones

### Background

Our data is from the Game of Thrones wiki.

* We collected total of 54 major characters that are quite important in the story.

* The data includes the character name, allegiance, alive or dead status (death is one of the most important events in GoT), causes of death, number of appearance, origin, religion, culture and portrayal.

* In addition to organizing lots of character data, our visualization answers interesting questions about the television series such as: How many major characters have died thus far? What is the most popular cause of death in the book? Which houses have the most major characters?

* Another purpose of this visualization is we want people who haven’t seen this book (such as a member of our group) to gain knowledge of this book.

### Data Collection & Cleaning

* Our first dataset is in graphml format. However, D3 doesn't support this format and it is hard to convert to csv format file. So, we wrote Python script to collect the major characters of GoT data from its wiki web pages into a csv file.

* We then manually cleaned the raw data as below: 

  - Removed the comma separated number for season data 
  - Removed the “(see below)” hyperlink for appearance data 
  - Removed “house” words for allegiance data.

* We initially thought putting all information except houses and death cause of the characters as the Collapsible Tree nodes in visualization will be great, but not all characters are provided with this data on wiki and it will make the edges line more complicated among characters. Due to the same reason, we didn’t put the killer of the characters in visualization.

### Vis-System Description

* The vis-system is pretty straight forward. It contains two graphs.

* The main graph is a chord graph. The inner labels are 54 main characters listing in descending order of number of appeared episodes. Outer arcs are houses they allegiance to. The width of arcs stands for the total number of appearances of all characters who are effectively loyal to this house. Outer arc label is the house name and appeared number. The last piece is inner strings which link houses and characters.

* User can click “Show Deceased” button under main graph switch to the cause-of-death graph.

* The cause-of-death graph is similar to the main graph. In this chord graph, inner labels are changed to “death cause”, and outer arcs are deceased characters. Width of arcs Represents the number of appearances of this character.

### Interactions

* In the main graph, move mouse to the character label will generate a pop up window displaying the characters information. We made this pop up window as a table because character’s data is highly discrete. For example, it’s very hard to find inner connections between character’s gender and house.

* Meanwhile, houses the character loyal to will highlighted and unrelated houses will Hide. The title will show the characters name and appeared number.

* Cause-of-death graph have similar interactions with main graph.

* Move mouse to the house name will hide strings linked to unrelated characters. Users can also click outer arcs and labels to maintain in this view.

### Interesting Results

* The first interesting result is roughly 40% major characters deceased. Nobody is safe. And there are various ways of death. Even the most popular way, blade, only kill 7 characters.

* Another interesting result is we found Night’s Watch are more important than House Stark (Night’s watch ranks higher than Stark). Even if the Night’s Watch has only three characters appear, but two of them (Jon and Samwell) appear very often. In contrast, more than half of the roles of the Stark appear less frequently.

* The last interesting result is 54 characters loyalty to 32 houses. We initially expected major characters only exist in several famous houses like Lannister or Stark. We think this is exactly the reason why this book is attractive: small house also has a big influence, like an epic.


### How to use

1. open simple server using python -m SimpleHTTPServer 8888
2. find the system folder and enter
3. users now can click outer arcs and labels.

@2018, Ruida Xie, Tong Wang, All rights reserved
