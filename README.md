Download Link: https://assignmentchef.com/product/solved-hungry-squirrel
<br>
For the final exam project, you will write a game application called “Hungry Squirrel”.  In this game, there is a Squirrel in a maze looking for nuts.  You will guide the squirrel to find and collect the nuts. There are two types of nuts available in the maze, Almonds and Peanuts.  As the squirrel eats the nuts, it gains nutritional points. Once the squirrel finds all the nuts in the maze, the game is over. To implement this game, you will define 8 classes: Maze class, Entity class, Squirrel class, Wall class, Nut class, Almond class, Peanut class, and HungrySquirrelGame class. Each class is described in details in the following sections.

The following class diagram shows the class hierarchy between the classes:

<table width="100%">

 <tbody>

  <tr>

   <td>    Entity</td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td>     Nut</td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td> Squirrel</td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td>   Peanut</td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td>  Almond</td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td>Movable</td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td></td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td>Wall</td>

  </tr>

 </tbody>

</table>

<table width="100%">

 <tbody>

  <tr>

   <td>&lt;impl&gt;</td>

  </tr>

 </tbody>

</table>







In this document, you will find each class defined in details. There is enough information to help you build and implement this game. The class description does not provide or describe the Constructors, setter/getter methods or toString method, you should add them as needed. You are not required to implement the class attributes and methods exactly as specified here; feel free to add/remove attributes or methods as you see fit. However, you must define each class and do not make modifications to the class names.

1.     Entity Class

You must define an abstract “<strong><em>Entity</em></strong>” class.  Two types of entities exist in the Maze: Nut and Squirrel.  Each entity has three attributes:

<ol>

 <li><strong><em><u>symbol</u></em></strong>: This instance variable is a character symbol by which an entity is identified on the Maze. For example, a squirrel is represented by ‘@’. Each nut will be represented by the first character of its name (e.g. Almond will be represented by ‘A’).</li>

 <li><strong><em><u>row</u></em></strong>: This instance variable is the row position of the entity in the maze.</li>

 <li><strong><em><u>column</u></em></strong>: This instance variable is the column position of the entity in the maze.</li>

</ol>

The abstract <strong><em>Entity</em></strong> class contains an abstract method:

<strong><em><u>public void create();</u></em></strong>




The <strong><em>Entity</em></strong> class contains the following concrete method:




<strong><em><u>public Entity put(int newRow, int newCol)</u></em></strong>




This method puts an entity at location (newRow, newCol) in the maze. You have to pay attention because the entity cannot move to a location already filled with a wall (i.e. ‘*’).  This method returns an Entity that was replaced in the new location. This can be useful when moving the squirrel and figuring out if it ate a nut.

2.     Movable Interface

The <strong><em>Movable </em></strong>interface declares a single method and is implemented by Entities that can move in the maze (e.g. Squirrel)

<strong><em><u>void move(char direction);</u></em></strong>

3.     Squirrel Class

You must define the Squirrel class. The squirrel is represented by the “@” symbol in the maze. It is able to move up, down, left and right.  The initial location of the squirrel is determined by the user. The program must prompt the user to enter the starting row and column of the squirrel. The squirrel cannot move to where there is a wall (i.e. ‘*’).  Once the squirrel moves over a nut, it eats the nut and collects points.  Each type of nut carries a different point.

The <strong><em>Squirrel</em></strong> class is inherited from the <strong><em>Entity</em></strong> abstract class. The Squirrel class implements the <strong><em>Movable</em></strong> interface. The Squirrel class contains two attributes:

<ol>

 <li><strong><em><u>pointsCollected</u></em></strong>: This attribute provides the total points a squirrel object has accumulated as a result of gathering nuts.</li>

 <li><strong><em><u>totalNutsEaten</u></em></strong>: This attribute provides the total number of nuts eaten thus far.</li>

</ol>

The Squirrel class defines the following methods:

<strong><em><u>public void create()</u></em></strong>

<strong><em><u> </u></em></strong>

This method provides the implementation of the abstract method in the <strong><em>Entity</em></strong> superclass.  This method asks the user to provide the initial location of the squirrel in the maze.  You have to make sure the location provided by the user is valid and available. If the user provides an invalid or unavailable location, you will have to ask the user to input a new set of data.  You must continue until the user provides a valid position. Keep in mind that a squirrel cannot be placed where there is a wall ‘*’.




<strong><em><u>public void move(char direction)</u></em></strong>

This method moves the squirrel one position to the direction specified.

4.     Nut Class

Nut is an abstract super class that is inherited from Entity super class.  There are two types of nuts available: Almond and Peanut. When a squirrel eats a nut, it’ll gain points. Once a nut is eaten, it should disappear from the maze. There are total of 5 nuts created. The nuts locations are created randomly in the maze and have to be placed in a valid location in the maze, meaning that a nut cannot be put in a position occupied by a wall (*), a squirrel (@) or a previously created nut. The number of peanuts / almonds are based on a random 50% chance.




The <strong><em>Nut</em></strong> class contains the following attribute:




<ol>

 <li><strong><em><u>Total Nuts</u></em></strong>: This class variable is a constant variable that represents the total number of nuts that will be created for this game (For this project, we create 5 nuts).</li>

 <li><strong><em><u>NutritionPoints: </u></em></strong>This instance variable stores then nutrition points of the nut.</li>

 <li><strong><em><u>Name: </u></em></strong>This String instance variable is the name of the nut (“Almond” or “Peanut”)</li>

</ol>

The <strong><em>Nut</em></strong> class implements the following methods:




<strong><em><u>void create()</u></em></strong>

<strong><em><u> </u></em></strong>

This method implements the abstract method in the <strong><em>Entity</em></strong> superclass.  This method randomly creates the location of the nuts.  You have to make sure the locations are valid and available. Keep in mind that a nut cannot be placed over a wall (*), a squirrel (@) or a previously created nut. In other words, it can only be placed where there is a blank space (‘ ‘).

5.     Almond Class

Almond is a type of a Nut .  An almond is represented by the character symbol ‘A’ in the maze.  An almond carries 5 nutritional points; therefore, when the squirrel eats an almond, it gains 5 points.




The <strong><em>Almond</em></strong> Class is inherited from the <strong><em>Nut </em></strong>abstract super class. The <strong><em>Almond</em></strong> class defines the following attribute:

<ol>

 <li><strong><em><u>Nutrition Points</u></em></strong>: This class variable is a constant variable that represents the nutrition points an almond carries.</li>

</ol>

6.     Peanut Class

Peanut is a type of a Nut.  A peanut is represented by the character symbol ‘P’ in the maze.  A peanut carries 10 nutritional points; therefore, when the squirrel eats a peanut, it gains 10 points.




The <strong><em>Peanut</em></strong> Class is inherited from the <strong><em>Nut </em></strong>abstract super class. The <strong><em>Peanut</em></strong> class defines the following attribute:

<ol>

 <li><strong><em><u>Nutrition Points</u></em></strong>: This class variable is a constant variable that represents the nutrition points a peanut carries.</li>

</ol>

7.     The Maze Class

You must define the <strong><em>Maze</em></strong> class.   The maze is a 20 x 50 rectangular area represented by a 2-dimensional Entity array.   The walls in the maze are represented by ‘*’ and available positions by blank space. The maze structure is read from a text file “Maze.txt” (The Maze.txt will be provided to you). A squirrel is able to freely move in blank spaces in the maze.

**************************************************

********************                **********************

********************                **********************

********************                **********************

***********                                                        ***********

***********                                                        ***********

*                                                                                              **

*                                                                                              **

*                                                                                              **

*                           **********************                       **

*                           **********************                       **

*                           **********************                       **

*                           **********************                       **

*                                                                                              **

*                                                                                              **

*                                                                                              **

*****                            **************                  ********

************                                                  *************

*****                                                                        *********

**************************************************




The <strong><em>Maze</em></strong> class defines the following attributes:

<ol>

 <li><strong><em><u>Max_Maze_Row</u></em></strong>: This <strong><em>class variable</em></strong> is a constant variable that defines the maximum number of rows in the maze (it should be set to 20 rows).</li>

 <li><strong><em><u>Max Maze Column</u></em></strong>: This <strong><em>class variable</em></strong> is a constant variable that defines the maximum number of columns in the maze (it should be set to 50 columns).</li>

 <li><strong><em><u>maze[][]</u></em></strong> : This <strong><em>class variable</em></strong> is a 2-dimentional Entity array that contains the full maze and the entities.</li>

</ol>

The <strong><em>Maze</em></strong> class implements the following methods:

<strong><em><u>public static void create(String filename)</u></em></strong>

This method reads the file passed to the method (i.e. Maze.txt) and initializes the 2-dimentional array with the maze content provided in the file.

<strong><em><u>public static void display()</u></em></strong>

This method displays the maze structure and the containing entities.

<strong><em><u>public static boolean available(int row, int col)</u></em></strong>

This method takes a row and a column and determines if the location at the row and the column is blank space. If it is, it returns true; otherwise, it returns false.




8.     HungrySquirrelGame Class

The <strong><em>HungrySquirrelGame</em></strong> class defines the main method.  The flow of the main method can be something like this:

<ol>

 <li>Call the create method of the Maze class to create the maze.</li>

 <li>Instantiate a squirrel object. This creates the squirrel and puts the squirrel in the maze based on the user input.</li>

 <li>Instantiate an array of Nut objects and determine and create the type of nuts (almond or peanut).</li>

 <li>Display the maze with all the entities created.</li>

 <li>Accept user input to move the squirrel.</li>

 <li>For every move the full maze with all the entities should be displayed.</li>

 <li>Every time the squirrel collects a nut, a message must be output displaying the points collected for the new nut and total points collected thus far.</li>

</ol>

<strong>!!! Squirrel ate Almond and gained 5 points (Total 15 points) !!! </strong>

<strong> </strong>

<ol start="8">

 <li>Once the squirrel collects all the nuts, a message must be displayed and the game is over.</li>

</ol>

<strong>“Squirrel successfully collected all the nuts. Total points 30.”</strong>

<strong>“Thank you for playing this game”</strong>

<strong> </strong>

<strong> </strong>**************************************************

********************                    **********************

********************                    **********************

********************                    **********************

***********                                                          ************

***********                                                          ************

*                                                                                                  **

*                                                                                                  **

*                                                                                                  **

*                           **********************                           **

*                           **********************                           **

*                           **********************                           **

*                           **********************                           **

*                                                                                                  **

*                                                                                                  **

*                                                                                                  **

*****                            **************                      ********

************                                                      *************

*****                                                                            *********

**************************************************




Enter the Squirrel position (row , column): 1,1

Position not available. Try again!

Enter the Squirrel position (row , column): 7,23

User input accepted.

Enter commands u,d,l,r to move Up, Down, Left, and Right:

**************************************************

********************                   **********************

********************                   **********************

********************                   **********************

***********                                                         ************

***********                                                         ************

*                                          @                                                    **

*                                                                                                  **

*                 A                                                               P             **

*                           **********************                           **

*                           **********************                           **

*           P              **********************                           **

*                           **********************                           **

*                                                                                    A           **

*                                                                                                  **

*                                                                                                   **

*****                            **************                      ********

************                                                      *************

*****                                 P                                         *********

**************************************************




Enter command: d

**************************************************

********************                   **********************

********************                   **********************

********************                   **********************

***********                                                         ************

***********                                                         ************

*                                                                                                 **

*                                          @                                                    **

*                 A                                                               P             **

*                           **********************                           **

*                           **********************                           **

*           P              **********************                           **

*                           **********************                           **

*                                                                                    A           **

*                                                                                                  **

*                                                                                                   **

*****                            **************                      ********

************                                                      *************

*****                                 P                                         *********

**************************************************
















**************************************************

********************                   **********************

********************                   **********************

********************                   **********************

***********                                                         ************

***********                                                         ************

*                                                                                                 **

*                                                                                                  **

*                                                                                                  **

*                           **********************                           **

*                           **********************                           **

*                            **********************                           **

*                           **********************                           **

*                                                                                                  **

*                                                                                                  **

*                                                                                                   **

*****                            **************                      ********

************                                                      *************

*****                                 @                                        *********

**************************************************




Squirrel successfully collected all the nuts. Total points 40

Thank you for playing this game

9.     Extra Credit (+3 Points)

Define a new entity called “<strong><em>PoisonousCashew</em></strong>”. Poisonous cashews are bad for the squirrel and carry negative nutrition points (-15 points).  If a squirrel collects poisonous cashews and its total points become negative, the squirrel dies and the game is over. There are total of 5 poisonous cashews in the maze.


