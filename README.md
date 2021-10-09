# DATA602 Yugioh Regression Analysis
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

## EDA Findings
* The "releases" category contained the card's release in every single region. However for the most part, they are all dropped within the same year (give or take a few for the january or december drops).
* The following columns serve no real purpose regarding my buisness question
    * Number
      * has nothing to contribute towards my buisness question
    * naming_condition
      * Changing the name on the field has no bearing on the monster's strength
    * text
    * pendulumn_text
  * The following Categorical variables will need dummy variables (one hot encoding):
    * attribute
    * Type
    * monster_types
    * materials


## Regression Results
The training R^2 was super close to the test R^2 and really high. So much so that I believe it could be sampling error

However, there may be some factor that is leaking into my error term that is causing this pattern:
* It could be "bad data" caused by the approach i took when filling the NA values. By filling all the empty cells with what I deemed to be an "unattainable stat", I naievely skewed the data which may have caused my regression to quite easily predict one of those unattainable values.
   *  "CAUTION: if you want to use this for Machine Learning / Data Science: from a 
      Data Science perspective it is wrong to first replace NA and then split into 
      train and test... You MUST first split into train and test, then replace NA by 
      mean on train and then apply this stateful preprocessing model to test
      Aug 28 '19 at 9:18"

* This could also be due to the monster_types not being seperated out. There's a prominent skew towards effect monsters due to the competative metagame relying on effect monsters. Unfortunately I caunt really account for it without completely reforming my data.


## Dataset predictions
I was able to predict attack values with a r-squared of 99.99998675959489%. I attempted regularization via Ridge, OLS, and Lasso but found no benefit to adding regulariztion to our models.

## Future plans
The following could be applied in the future
* Finding a different way to fill my NA values that has less impact on the regression itself.
   * "first split into train and test, then replace NA by mean on train and then apply this stateful preprocessing model to test" ~ Fabian Werner
* Seperating out the monster_types to distribute the weight of each of the different monster types in a more fair way
* Update the card pool to include cards up to the "Lightning Overdrive" set to express the impact link monsters have on the various features of the dataset
