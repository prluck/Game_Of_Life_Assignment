Base Game-Of-Life jscript
https://editor.p5js.org/patrickrluck/full/7iRV5Ee_g

Altered Game-Of-Life jscript
https://editor.p5js.org/patrickrluck/full/mFTh9QqQl

The base GOL java script runs a base version that follows the following rules:
  If cell is alive and total living neighbors is greater than 4:
    Cell dies
  If cell is alive and total living neighbors is 1 or less:
    Cell dies
  If cell is dead and total living neighbors is equal to 3:
    Cell is born
  Otherwise, cell retails it's current state


The altered GOL follows a different set of rules
  Every cycle, the cell follows two seperate formulas to determine its growth or decay

  The first is 1 - |(2/3)*neighborSum - 2|.
    This creates a peak positive growth at neighborSum = 3 and maxes out decay at neighborSum = 0 and neighborSum >= 6
  The second is a two part function
    If neighborSum <= 3: (1/3)*neighborSum - 1
    If neighborSum > 3: 1.5 - 0.5*neighborSum
    This creates a peak where no growth and no decay happens at neighborSum = 3 and maxes out decay at neighborSum = 0 and neighborSum >= 5
  These two formulas mirror the original rule's system of preferring 3 neighbors for growth and punishing having more than 4 neighbors and less than 2
  These two formulas are then blended by multiplying them ot the current state of the cell, maxing out the first formula when the cell is fully dead, and maxing out the second when the cell if fully alive

Thus, the cell is more likely to die when alive and more like to live when dead.
The result is a rather strange maze-like generation system that was unexpected. Not sure why it works the way it does, but it's neat.
