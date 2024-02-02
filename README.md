# LetterBuddies 🕺🏻
🙌🏻 Welcome to "Letter Buddies" – a word-guessing game AKA hangman! 🎮 <br> 
*(p.s. this is actually just hangman, but to make it seem like i've done a lot, this is called letter buddies)* 

Choose from four lame categories, each holding a secret word for you to unravel.  You've got 5 chances to crack the code. Make every click count!

Every click on the keyboard unfolds the letters or brings you closer to a surprise. Hohoho! Can you conquer the words and become the ultimate "Letter Buddies" champion? Simple rules, unexpected surprises – let the guessing games begin ~~ 🔠👾

## PLAY!! 🕹️
CLICK ME >> *https://teehweehwee.github.io/LetterBuddies/*

## Code Explanation 💬
The code consist of the following components:

### index.html
- `link href` to import fonts from google fonts
- `transparencyOverlay` & `lobbyPage` & `categoriesPage` & `gameplaypage`<div> are different containers storing content thats act as a separate page
- `word-display` a placeholder that display the letters/underscores as you play the game
- `button-container` a placeholder that holds all the letters button generated using Javascript
- `remainingGuesses` inline container that display the changing number of remaining guesses
### style.css
- provides styling of my html elements
- some `diplay` are set as `none`, by default these elements are hidden and will be displayed once triggered e.g #winMessage

### main.js
- `DOMContentLoaded` is an event listener

- `variables`
  1. `lobbyPage`,`transparencyOverlay`,`categoriesPage`,`gameplaypage`,`winMessage`,`loseMessage` - control when they appear on the screen (access them through DOM)
  2. `rulesButton`,`startButton`,`categoryButtons` - each buttons have its own event upon instructions, e.g. rulesButton: Mouseover & Mouseout; startButton: onClick; catergoryButtons: Onclick
  3. `displayUnderscore` - defined at the start as an empty array to store displayed word letters 
  4. `answerKey` - holds the word to be guessed
  5. `remainingGuesses` - track remaining attempts
  7. `updateGuesses` - a variable connected to the /span/ element to update remaining guesses 
  8. `keyboard` - a local variable (only be called after `generateButton` because original HTML, does not have keyboard). `for each` letter of the keyboard being clicked, run `controlClick` 

- `functions`
  1. `disableStartButton` -  don't allow the click on "start" button by setting disabled as true
  2. `showTransparencyOverlay` - show the rules page then enable click on "start"
  3. `hideTransparencyOverlay` - hides the rules page
  4. `enableStartButton` - allow the click on "start" button by setting disable as false
  6. `getRandomWord` - using `math random` to get a random number and choose the word based on the index defined by the random number from category array 
  7. `startGame()` - to navigate to category page, by hiding the "start" button and displaying categories selection
  8. `displayWord()` - display the updated state of word being guessed 
  9. `generateButton()` - string of all alphabet arranged in sequence that i want, use `.split` to put them into array of individual elements, using `.map` to create buttons based on their letters, then put the generated keyboard into the button container in HTML
  10. `controlClick` - based on each keycaps clicked, will return the id of the corresponding letter and then run the `make guess` function based on the selected keycap
  11. `makeGuess` - to process user guesses, checks if the guess is correct, updates the displayed word, and handles game over scenarios

- `switch case`
   1. `switch`: based on the category user have chosen, `case`: run `randomWord` based on that category, run `.split` to separate each letters into an array containing its individual letters,  `for loop` update display underscore, run `displayWord`,redefine the null `answerKey` to an answer key that contains the array of the selected word. This `answerKey` can be used a test against the user input.

### wordbank.js 
- a separate Javascript file containing arrays of words sorted by the categories 
- `module.export` exporting an object of arrays that can be accessed in the main.js

## Screenshots 📸
### Rules Page
![Rules](/imagedump/ssrulespage.png)
### Game Play Page
![Gameplay](/imagedump/ssgameplay.png)

## Future Enhancements 💄
- Allow the player to restart the game without refreshing AKA Game Reset 
- Create more categories & larger wordbank
- Instead of hardcoding number of tries, the difficulty can be based on the random word AKA Using word length
- On top of remaining guesses -1, act graphics to enhance user experience when guessing the wrong letter
- MY FAVOURITE OUT OF ALL: audio 🎧