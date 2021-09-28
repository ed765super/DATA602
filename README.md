# DATA602
## Data = YGO_Cards_v2.csv
   Recieved from Kaggle.com (https://www.kaggle.com/rushikeshhiray/yugioh-normal-monster-cards)
   
   According to Chris Kirkham, the user on Kaggle who scrapped the data, this data was scrapped using an YGOHub API.

   The API used could not correctly scrape cards with & or # in their name. Thus Chris just left them out. Fortunately, this only leaves out around 35 cards. Since there are    nearly 6000 monster entries, this should not have much of an affect on the data overall.
   
## Project Description:
   Background information and Buisness Question
The YUGIOH trading card game was launched by Konami back in 2002.

(The following explination of how yugioh is played is grabbed from the following site: https://www.dacardworld.com/gaming/yu-gi-oh-cards/how-to-play)

Each match in YuGiOh consists of 3 duels in a best-of-3 format. During a duel, each player starts with 8000 Life Points and a winner is declared in one of the following ways:

Reduce your opponent's Life Points to 0
If and when it is time to draw a card, your opponent is unable to do so
With a card's special effect
Before you begin a duel, you must follow these steps:

Players should shuffle their decks
Place all decks face-down in their specified Deck Zones
Players show their side deck to their opponent and count all the cards in each deck
If this is the first match of the duel, the winner of a coin flip or rock-paper-scissors decides which turn they would like in the duel. Otherwise, the loser of previous duel decides who goes first
Draw 5 cards from the top of the Main Deck and begin.
Over the years, a whole slew of cards were printed; morphing the metagame into what it is today. Ever since the prining of "Chaos Emperor Dragon - Envoy of the End", Konami has released updates to the ban list as a way to balance their game. However, with the release of the October 2021 banlist, it has become clear to the community that Konami intends to use their banlist more as a way to sell their upcoming products rather than balance their game. As a software developer and yugioh fan, I want to understand what drives attack levels to be as high as they are and determine whether that has any effect on what cards appear on the banlist.


  The following is exploratory data analysis (EDA) on the various cards of Konami's hit trading card game Yu-gi-oh. This assignment will include:
    
    Output of professional quality where 
      Charts properly labeled (axis labels, titles, …)
    
    (70%) Completeness of exploratory analysis
    
    (5%) Discussion of business question / objective that is being analyzed
    
    (5%) Profiling of data (observations, missing values, data types)
    
    (10%) Relevant categorical variables analyzed, and cleaned, if necessary.
    
    (10%) Numerical variables analyzed (distributions, five number summary, …)
    
    (30%) Exploration of relationships between key categorical and numerical variables
    
    (10%) Discussion of what you have observed throughout your analysis
