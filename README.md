# Jeopardy Hanami

Welcome to your new Hanami project!

## Setup

How to run tests:

```
% bundle exec rake
```

How to run the development console:

```
% bundle exec hanami console
```

How to run the development server:

```
% bundle exec hanami server
```

How to prepare (create and migrate) DB for `development` and `test` environments:

```
% bundle exec hanami db prepare

% HANAMI_ENV=test bundle exec hanami db prepare
```


# Ideas

A user:
- [ ] can register
- [ ] can login
- [ ] can add answers in different categories

A board includes:

- Categories
- answers and names for each category

Board config:

- When starting a game, the players pick a number of categories and clues
- The app will pick random categories and random clues for those categories

Game logic:

1. logged in players will be sorted randomly
2. current player is the first player
3. if there are available options
   4 - - the first player picks a category and a value
   5 - - the player then has to pick the name from a list
   6 - - if it's the wrong name, the rest of the player get to guess picking an option from a list
   7 - - - (a player can't answer an option they added, the app should change the option if a user picks one that's them)
   8 - - - (players winning this extra change get twice the points)
   9 - - - turn goes to the next player in the list (back to step 3)
   10 - - if it's the correct name, the player gets the points and plays again (back to step 3)
   11 - if there are no more options, show the results
