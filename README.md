Download Link: https://assignmentchef.com/product/solved-comp250-assignment-1-a-civilization-inspired-strategy-game
<br>
For this assignment you will write several classes as a first step toward building a very simplified version of a Civilization-inspired strategy game. Make sure to follow the instructions below very closely. Note that in addition to the required methods, you are free to add as many other <strong>private </strong>methods as you want. You can also add public toString() methods in each class to help with the debugging process. No other additional non-private method is allowed. <strong>No additional (</strong>public <strong>or </strong>private<strong>) fields are allowed.</strong>

Let’s start by creating a skeleton for some of the classes you will need. Note that later we will define a new data type called Tile. For the moment just go ahead and use it. It is normal that your code will not compile until you create a public class called Tile.

<ul>

 <li>Write an abstract class Unit which has the following private fields:

  <ul>

   <li>A Tile representing the position of the unit in the game.</li>

   <li>A double representing the health points (hp) of the unit.</li>

   <li>An int representing the available moving range of the unit.</li>

   <li>A String representing the faction to which the unit belongs. The faction determines to which group of people this unit belongs. Examples of factions in civilization are: Barbarians, Aztecs, Sumerians, Romans, Greeks, etc.</li>

  </ul></li>

</ul>

The class must also have the following public methods:

<ul>

 <li>A constructor that takes as input a Tile indicating the position of the unit, a double indicating its hp, an int indicating its moving range, and a String indicating its faction. The constructor uses its inputs to initialize the corresponding attributes.</li>

 <li>A final getPosition() method to retrieve the position of <u>this </u>Unit.</li>

 <li>A final getHP() method to retrieve the health points of <u>this </u>Unit.</li>

 <li>A final getFaction() method to retrieve the faction of <u>this </u>Unit.</li>

</ul>

<ul>

 <li>All of the following must be subclasses of the Unit class:

  <ul>

   <li>Write a class Settler derived from the Unit The Settler class has the following public method:</li>

  </ul></li>

</ul>

∗ A constructor that takes as input a Tile which contains the position of the settler, a double indicating its hp, and a String indicating its faction. The constructor uses the inputs to create a Settler with the above characteristic and moving range equal to 2.

<ul>

 <li>Write a class Worker derived from the Unit The Worker class has the following private field:</li>

</ul>

∗ An int indicating the number of jobs already performed by the worker.

The Worker class has also the following public method:

∗ A constructor that takes as input a Tile which contains the position of the worker, a double indicating its hp, and a String indicating its faction. The constructor uses the inputs to create a Worker with the above characteristic, moving range equal to 2, and number of jobs performed equal to 0.

<ul>

 <li>Write an abstract class MilitaryUnit derived from the Unit The MilitaryUnit class has the following private fields:</li>

</ul>

∗ A double indicating the attack damage of the unit.

∗ An int indicating the attack range of the unit.

∗ An int indicating the armor of the unit.

The MilitaryUnit class has also the following public method:

∗ A constructor that takes as input a Tile which contains the position of the unit, a double indicating its hp, an int indicating its moving range, a String indicating its faction, and three additional fields: one double indicating its attack damage and two ints indicating attack range and armor respectively. The constructor uses the inputs to create a MilitaryUnit with the above characteristic.

<ul>

 <li>Write a class Warrior derived from the MilitaryUnit The Warrior class has no fields, but it has the following public method:</li>

</ul>

∗ A constructor that takes as input a Tile which contains the position of the warrior, a double indicating its hp, and a String indicating its faction. The constructor uses the inputs to create a MilitaryUnit with the above characteristic, moving range equal to 1, attack damage equal to 20<em>.</em>0, attack range equal to 1, and armor equal to 25.

<ul>

 <li>Write a class Archer derived from the MilitaryUnit The Archer class has the following private field:</li>

</ul>

∗ An int indicating the number of arrows available to the archer.

The Archer class has also the following public method:

∗ A constructor that takes as input a Tile which contains the position of the archer, a double indicating its hp, and a String indicating its faction. The constructor uses the inputs to create an Archer with the above characteristic, moving range equal to 2, attack damage equal to 15<em>.</em>0, attack range equal to 2, armor equal to 0, and 5 available arrows.

You can now leave these classes as they are, we will come back to them later. Let’s instead focus on the two other classes:

<ul>

 <li>Write a class ListOfUnits. The purpose of this class is to implement your own arraylist of Unit. We want to stress once again that you are not allowed to import any class for this assignment! The class ListOfUnits must have the following private fields:

  <ul>

   <li>An array of Units which will be used to store the units that are part of the ListOfUnits.</li>

   <li>An int indicating the size of the ListOfUnits, i.e. how many units have been stored in this list.</li>

  </ul></li>

</ul>

The class must also have the following public methods:

<ul>

 <li>A constructor that takes no inputs and creates an empty ListOfUnits. To do so, the fields should be initialized with an array of size 10. No units should be stored in the array at this moment. The size of the ListOfUnits should reflect this.</li>

 <li>A size() method that takes no inputs and returns the number of units that are part of <u>this </u>ListOfUnits.</li>

 <li>A getUnits() method which takes no inputs and returns an array containing all the units that are part of <u>this </u>ListOfUnits. This array should not contain any null</li>

 <li>A get() method which takes as input an int and returns the unit at the specified position in <u>this </u> If the integer received is out of range, i.e.   negative or greater than or equal to the number of units in the list, then the method should throw an IndexOutOfBoundsException.</li>

 <li>An add() method which takes as input a Unit and does not return any value. The method adds the Unit at the end of <u>this </u> If not enough space is available, then the method should resize the array of units. The capacity of the array should increase by a factor of 1.5 using the following formula:</li>

</ul>

new_capacity = old_capacity + old_capacity/2 + 1

This is a great place to create your own private method to performs such operation. Warning: make sure to not “lose” any of the units from the list.

<ul>

 <li>An indexOf() method which takes as input a Unit and returns an int indicating the position of the <strong>first </strong>occurrence of the specified element in <u>this </u> If no such unit exists, then the method returns −1. Remember that when comparing reference types you do not want to use ‘==’.</li>

 <li>A remove() method which takes as input a Unit and returns a boolean. The method removes the <strong>first </strong>occurrence of the specified element from the array of units of <u>this </u> If no such unit exists, then the method returns false, otherwise, after removing it, the method returns true. Note that this method <strong>removes a unit from the list if and only if such unit is <u>equal </u>to the input received</strong>. For example, it is not possible to remove an Aztect settler in place of a Sumerian settler. After the unit has been removed from the array, the subsequent elements should be shifted down by one position, leaving no empty slot in the array. No resizing of the array is necessary!</li>

 <li>A getArmy() method that takes no inputs and returns an array of MilitaryUnit The array should contain all MilitaryUnits that are part of <u>this </u>list. Note that not all units in the list are military units. A ListOfUnits may include also setters and workers. <strong>The array returned by the method should not contain any </strong>null <strong>elements.</strong></li>

</ul>

<ul>

 <li>Write a class Tile. You can think of a Tile as a square on the board on which the game will be played. A Tile must have the following private fields:</li>

 <li>An int indicating the x-coordinate of the tile.</li>

 <li>An int indicating the y-coordinate of the tile.</li>

 <li>A boolean indicating whether or not a city has been built on the tile.</li>

 <li>A boolean indicating whether or not the tile received some “improvements”.</li>

 <li>A ListOfUnits containing all the units positioned on the tile. This is where you will be using your own implementation of an arraylist of units.</li>

</ul>

The class must also have the following public methods:

<ul>

 <li>A constructor that takes as input two ints indicating the x and the y coordinate respectively. The constructor creates a Tile with the specified coordinates. A new tile is not a city, nor it has ever been improved. It also hosts no units. You must represent this by initializing its corresponding field with an empty ListOfUnits.</li>

 <li>A getX() and a getY() method which return the x and the y coordinate of the tile respectively.</li>

 <li>A isCity() method which returns whether or not the tile is a city.</li>

 <li>A isImproved() method which returns whether or not the tile has been improved.</li>

 <li>A foundCity() method which turns the tile into a city if it wasn’t already.</li>

 <li>A buildImprovement() method which improves the tile if it wasn’t already.</li>

 <li>An addUnit() method which takes as input a unit and adds it to the tile’s ListOfUnits. Note that a military unit can be added to the tile if and only if no military unit of a different faction (the enemies’ army!) is stationed here. Non-military units can always be added to the tile. The method returns true if the unit was successfully added to the list, false</li>

 <li>A removeUnit() method which takes as input a unit and removes it from the tile’s ListOfUnits. The method should also return a boolean indicating whether or not the operation was successful.</li>

 <li>A selectWeakEnemy() method which takes as input a String representing a faction. The method should return the enemy unit (i.e. any Unit with a faction different than the one specified) stationed on the tile with the lowest health. If no enemy unit is present, then the method returns null. If more than one enemy unit has the lowest health, then the one that appears first in the list should be returned.</li>

 <li>A static method called getDistance() which takes as input two tiles and returns a double indicating the distance between the two. Remember that given two points (<em>x</em><sub>1</sub><em>,y</em><sub>1</sub>) and (<em>x</em><sub>2</sub><em>,y</em><sub>2</sub>), the distance can be computed with the following formula:</li>

</ul>

<em>distance </em>= <sup>p</sup>(<em>x</em><sub>1 </sub>− <em>x</em><sub>2</sub>)<sup>2 </sup>+ (<em>y</em><sub>1 </sub>− <em>y</em><sub>2</sub>)<sup>2</sup>

We are now ready to go back to the classes we created at the beginning.

<ul>

 <li>In the class Unit go back to the constructor and make sure that when a unit with a specified position is created, such unit is also added to the ListOfUnits of the corresponding tile. Note that it is not always possible to do that (we cannot have enemy military units on the same tile!). If it is not possible to add the unit to the specified tile, then the constructor should throw an IllegalArgumentException.</li>

</ul>

To the Unit class add the following public methods:

<ul>

 <li>A moveTo() method which takes as input a Tile representing where the unit should be deployed. Note that a unit can be moved only if the target tile is within the moving range of the unit and <span style="text-decoration: line-through;">no enemy military units is already stationed there </span><strong>if the unit is allowed to be stationed on such tile (i.e. no military unit of different faction should ever be stationed on the same tile). Note that it is possible for non military units to be stationed on the same tile with other units from different factions. </strong>The method returns true if the unit is successfully moved, false Note that a target tile is within the unit range if the distance to the tile is less than the unit range plus one. Note also that when a unit is moved to a different tile this should be reflected both on the unit’s position as well as the old tile’s ListOfUnits.</li>

 <li>A receiveDamage() method which takes as input a double indicating the damage received by the unit. The method applies the damage to the unit by modifying the unit’s health. To do so, subtract the damage from the unit’s health points. Note that if the unit is stationed on a city, then the damage should be reduced by 10% before being applied. Moreover, if after the damage is applied the unit ends up having a non-positive health (0 or below), then the unit has been killed. In such a case, the unit should be removed from the game. To do that, remove the unit from the tile.</li>

 <li>An abstract method takeAction() which takes as input a Tile and does not return any value. This method should be abstract (thus, not implemented) because the action to take depends on the type of the unit.</li>

 <li>An equals() method which takes an Object as an input and returns true if the input matches this in type, position, health and faction. Otherwise the method returns false. • In the Settler class do the following:</li>

 <li>Implement the takeAction() The method takes a Tile as input. If this is the tile where the unit is stationed and it is not a city yet, then a city should be built on the specified tile. In such a case the unit is expended. To represent this, remove the unit from the tile. On the other hand, if a city is not built the method simply terminates.</li>

 <li>Override the equals() The method returns true if the Object received as input matches this in type, position, health and faction. Otherwise the method returns false. Note that you do not want to rewrite code that you have already written in the superclass. How can you access methods from the superclass that have been overridden?</li>

</ul>

<ul>

 <li>In the Worker class do the following:</li>

 <li>Implement the takeAction() The method takes a Tile as input. If this is the tile where the unit is stationed and it has not been improved yet, then an improvement should be built on the specified tile. If an improvement is built, then the number of jobs this worker has already performed should increase by one. If the worker reaches 10 jobs, then the unit is expended, i.e. the unit is removed from the tile.</li>

 <li>As for the Settler, override the equals() The method returns true if the Object received as input matches this in type, position, health, faction, and number of jobs performed.</li>

 <li>In the MilitaryUnit class do the following:

  <ul>

   <li>Implement the takeAction() The method takes a Tile as input. If the distance between the target tile and the position of the unit is greater than or equal to the unit’s attack range plus one, then an attack is not possible and the method terminates. Otherwise, the weakest enemy (a unit of a different faction) on the target tile is selected and receives a damage equal to <u>this </u>unit’s attack damage. Note that, if <u>this </u>unit is stationed on a tile which has been improved, then the damage inflicted should be increased by 5%. If no enemy unit is stationed on the specified tile, then the method does not do anything.</li>

   <li>Override the receiveDamage() The method receives a double as input indicating the damage the unit should receive. Before applying the damage to the unit (in the same way as receiveDamage() from Unit does), the damage should be multiplied by a multiplier which depends on this unit’s armor. The multiplier is a double equal to 100<em>/</em>(100 + <em>armor</em>). Once again, you do not want to rewrite code that you already have written in the superclass. How can you access methods from the superclass that have been overridden?</li>

  </ul></li>

 <li>In the Warrior class do the following

  <ul>

   <li>As for the Settler and Worker, override the equals() The method returns true if the Object received as input matches this in type, position, health, and faction. • In the Archer class do the following</li>

   <li>Override the takeAction() If the archer does not have any more arrows, it cannot attack. The method will instead take this time to reset the number of arrows to 5. On the other hand, if the archer has still available arrow it attacks like a MilitaryUnit and uses an arrow to do so. <strong>Note that the archer should use an arrow as soon as they try to attack (i.e. even in the case in which they are attacking a tile out of range or without any enemy unit)</strong></li>

   <li>As for the Settler, Worker and Warrior, override the equals() The method returns true if the Object received as input matches this in type, position, health, faction, and available arrows.</li>

  </ul></li>

</ul>