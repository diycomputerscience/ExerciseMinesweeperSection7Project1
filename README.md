<h1>Section 7 Project 1</h1>

<h2>Overview</h2>

In the previous few activities, we refactored code to make it better. What we have build till now is a Minesweeper user interface which is linked to a ```Board``` object. As things stand right now, the user interface displays squares that are mines in RED, and those which are not mines, have a count on them. The count denotes the number of neighbours that are mines.

In a real Minesweeper game, all the squares will initially be covered. A square is uncovered when a user left-clicks on it, and is marked as a mine, when a user right-clicks on it. Even though we have linked the user interface of the game to it's backend, we have not build features to allow a user to actually play the game. 

We will accomplish this over the next few projects. In this project, we will take the next baby step towards this goal. Instead of rendering squares with a special background color, or with a count, we will not render all squares on the board as shown below in Figure 1. They are all covered initially. 

![Minesweeper initial board](https://raw.github.com/diycomputerscience/MinesweeperImages/master/images/InitialBoard.jpg)

_**Figure 1**_

When a user clicks a square we will display it in RED if it is a mine, or display the count if it is not a mine, as shown below in Figure 2. This is the first project where we allow the user to interact with the game. 

![Minesweeper partially played game](https://raw.github.com/diycomputerscience/MinesweeperImages/master/images/PartiallyPlayedGame.jpg)

_**Figure 2**_

**Note:** We do not yet have to invoke the uncover method on ```Board``` when a left-click occurs. We will complete that cycle in a future project. For now, we will simply render details on the user interface, without invoking any methods on the ```Board``` object.

We have updated the method ```layoutSquares``` in ```UI.java``` to initially display the squares as plain ```JButton``` objects. The purpose of this activity is to get familiar with [event handlers in Java](http://docs.oracle.com/javase/tutorial/uiswing/events/index.html).

We have added a method called ```toString``` to ```Point``` so it can be printed easily (when we give an instance of ```Point``` to ```System.out.println()```, the String returned by that object's ```toString``` method is printed on the console).

We have also made some modifications in the test code. We have removed the test methods ```testMineIdentificationOnUI```, and ```testCountOnSquares``` from ```UITest.java``` and added a new test class ```ClickTest```,  which peforms functional testing of the application by actually running it and simulating user clicks on squares.

<h2>Steps For This Project</h2>

 1. Run UI and notice that all squares are displayed as plain buttons. Click on a square and notice that nothing happens.
 1. Run ```AllTests``` and verify that 36 tests are run, out of which one test fails.
 1. Try to determine what the ```layoutSquares``` method in ```UI``` does, and follow instructions specified by TODO: comments, in this method, to add an event handler to each JButton. This event handler should respond to a mouseEvent and render the Square either with a background color of RED if it is a mine, or display the count if it is not a mine.
 1. Run ```AllTests``` and verify that all tests pass.

<h2>Questions To Ponder</h2>
 1. What are anonymous inner classes and when should we use them ?
 1. What is a ```MouseAdapter``` ? Does it follow any design pattern ?
 