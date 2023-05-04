Download Link: https://assignmentchef.com/product/solved-csci-1133-assignment-3-bark-scale
<br>
<h1>Problem A.Bark Scale</h1>

Write a function sound(weight) that takes in a single positive integer value weight, representing the weight of a given dog, rounded to the nearest pound.  The function returns a string representing what the dog’s bark would probably sound like, based on the following scale:

<ul>

 <li>Less than 13 lbs: ‘Yip’</li>

 <li>13 – 30 lbs: ‘Ruff’</li>

 <li>31 – 70 lbs: ‘Bark’</li>

 <li>More than 70 lbs: ‘Boof’</li>

</ul>




<strong>Constraints</strong>:

<ul>

 <li>Do not import/use any Python modules.</li>

 <li>Do not use the input() function,</li>

 <li>Your submission should have no code outside of function definitions (comments are fine)</li>

</ul>




<strong>Examples</strong>:

&gt;&gt;&gt; sound(13)

‘Ruff’




&gt;&gt;&gt; sound(12)

‘Yip’




&gt;&gt;&gt; sound(50)

‘Bark’




&gt;&gt;&gt; sound(10000)

‘Boof’




Problem B. Text Adventure Choice

Some of the earliest computer games developed were <u><a href="https://en.wikipedia.org/wiki/Interactive_fiction">Interactive Fiction</a></u> games, in which the user’s environment is described in text, and the user makes choices using text commands.  In this problem and the next one, we’ll be developing a very simple text-based adventure game.  Every choice in this game will have exactly three options, so we can write a function that works for any of them.




Write a function choice(text,option1,option2,option3), that takes in four string values.  text is a string representing the prompt for a choice in a text adventure game, and option1, option2, and option3 are strings representing the three possible options.  The function should print out the text, and then print out the options (label them with 1., 2., and 3.).  Next, the input() function should be used to prompt the user to choose 1, 2, or 3; if the user does not choose one of those options, then the function must print “Invalid option” and prompt the user again (use a while loop for this).

Finally, the function should return the one character string that represents the user’s choice: ‘1’, ‘2’, or

‘3’.  See the examples below for an idea of how to format the printing and input functions: you don’t have to match it exactly but it should be roughly the same.




<strong>Constraints</strong>:

<ul>

 <li>Do not import/use any Python modules.</li>

 <li>Your submission should have no code outside of function definitions (comments are fine)</li>

</ul>




<strong>Examples</strong> (text in <strong>bold</strong> is returned, text in red is user input, text in <em>italics</em> is printed):




&gt;&gt;&gt; choice(“You have no idea how to approach this problem.”,

“Go to office hours”,

“Send an email to the TAs”,

“Post the problem online, there’s no way I’ll be caught”) <em>You have no idea how to approach this problem. </em>

<em> </em>

<ol>

 <li><em>Go to office hours </em></li>

 <li><em>Send an email to the TAs </em></li>

 <li><em>Post the problem online, there’s no way I’ll be caught </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> 1

<h2>‘1’</h2>




&gt;&gt;&gt; choice(“You must decide the fate of the galaxy.”,

“Destroy the robots”,

“Control the robots”,

“Merge with the robots?”)

<em>You must decide the fate of the galaxy. </em>

<em> </em>

<ol>

 <li><em>Destroy the robots </em></li>

 <li><em>Control the robots </em></li>

 <li><em>Merge with the robots? </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> 4

<em>Invalid option </em>

<em>Choose 1, 2, or 3:</em> Sing at the robots

<em>Invalid option </em>

<em>Choose 1, 2, or 3:</em> -2

<em>Invalid option </em>

<em>Choose 1, 2, or 3:</em> 2

<h2>‘2’</h2>




&gt;&gt;&gt; choice(“Choose a house.”,

“Black Eagles”,

“Slytherin”,

“Team Instinct”) <em>Choose a house.  </em>

<ol>

 <li><em>Black Eagles </em></li>

 <li><em>Slytherin </em></li>

 <li><em>Team Instinct </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> Black Eagles

<em>Invalid option </em>

<em>Choose 1, 2, or 3:</em> 3 <strong>‘3’ </strong>







<h1>Problem C. (20<em> points</em>)  Text Adventure Game</h1>

Using the function from the previous problem, write a function adventure() which takes in no arguments, and gives the user a sequence of choices, leading to one of several endings.  Since we want this problem to not be impossible to grade, you need to follow a very specific choice structure, namely the one outlined in the flowchart below:







Each diamond represents a decision, for which you must use your choice function from problem B.  Each arrow represents one of the three possible choices for that decision: 1, 2, or 3.  Each rounded box represents an ending to the story, which comes in one of two possible types: Good (the user succeeds in some way) or Bad (the user fails).  The story itself is entirely up to you, with one exception: you can’t use the one in the example below.  We will not be grading you based on the story’s quality, logic, originality, or grammatical correctness, so if you’re lazy and just want to put in empty strings for every single choice, that’s fine, but <strong>you must follow the choice structure in the flowchart above</strong>.




Your function should <strong>return</strong> the boolean value (not the string) True if the user reached a Good ending, or False if they reached a Bad ending.  You can put in a few additional print statements beyond the ones inside the choice function to better explain the story, but this is not required.




<strong>Hints: </strong>

<ul>

 <li>There are two basic ways to do this. You could put in nested if statements for every possible combination of decisions, which will result in a lot of repeated code, since there are multiple paths to two of the decision points.  Or, you could treat this as a <u><a href="https://en.wikipedia.org/wiki/State_diagram">state machine</a></u><a href="https://en.wikipedia.org/wiki/State_diagram">.</a>  In particular, if we label each decision as shown below, you’ll notice that every path through the flowchart <u>passes</u> <u>through</u><span style="text-decoration: line-through;">passes goes through</span> states (decisions) in an increasing order (a path may skip some states, but it will never go from a higher numbered state, down to a lower numbered one).</li>

</ul>




<ul>

 <li>You can take advantage of the above by using an extra variable to track what state the user is currently in (what number decision point they are currently at), and changing it every time they make a choice. For each state starting at 1 and ending at 5, check whether the user is in that state, and only give them the respective choice if they are.  Since all paths go through states in an increasing numerical order, you only have to check each state once.</li>

</ul>




<strong>Constraints</strong>:

<ul>

 <li>Do not import/use any Python modules</li>

 <li>Your submission should have no code outside of function definitions (comments are fine).</li>

 <li>You must use the choice() function from problem B.</li>

</ul>




<strong>Examples</strong> (text in <strong>bold</strong> is returned, text in red is user input, text in <em>italics</em> is printed.  Note that because you are required to have a different story than mine, the printed text should not match, but the same sequence of inputs should lead to the same return value):

&gt;&gt;&gt; adventure()

<em>You sneak into the dragon’s lair, with your comrades Wizard </em>

<em>McBlastyFace and Steve the Bard.  The dragon is fast asleep. </em>

<em> </em>

<ol>

 <li><em>Tickle the dragon on the nose </em></li>

 <li><em>Tell your team to start stealing things </em></li>

 <li><em>Tell your team to prepare for battle </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> 1




<em>The dragon sneezes out a fireball and incinerates you instantly. </em><strong>False</strong>




&gt;&gt;&gt; adventure()

<em>You sneak into the dragon’s lair, with your comrades Wizard </em>

<em>McBlastyFace and Steve the Bard.  The dragon is fast asleep. </em>

<em> </em>

<ol>

 <li><em>Tickle the dragon on the nose </em></li>

 <li><em>Tell your team to start stealing things </em></li>

 <li><em>Tell your team to prepare for battle </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> 4

<em>Invalid option </em>

<em>Choose 1, 2, or 3:</em> 2




<em>You can’t carry the entire hoard of loot. </em>

<em> </em>

<ol>

 <li><em>Take the pile of silk in the corner </em></li>

 <li><em>Take as much gold as you can carry </em></li>

 <li><em>Take the huge diamond nestled under the dragon’s claw </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> 1




<em>You and your team easily take all of the silk and escape quietly into the night. </em>

<h2>True</h2>




&gt;&gt;&gt; adventure()

<em>You sneak into the dragon’s lair, with your comrades Wizard </em>

<em>McBlastyFace and Steve the Bard.  The dragon is fast asleep. </em>

<em> </em>

<ol>

 <li><em>Tickle the dragon on the nose </em></li>

 <li><em>Tell your team to start stealing things </em></li>

 <li><em>Tell your team to prepare for battle </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> 3




<em>Who will lead the attack? </em>

<em> </em>

<ol>

 <li><em>Wizard McBlastyFace </em></li>

 <li><em>Steve the Bard </em></li>

 <li><em>Me, of course </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> 2




<em>Steve trips over a rock and the dragon wakes up. </em>

<em> </em>

<ol>

 <li><em>Tell Steve to sing to the dragon </em></li>

 <li><em>CHARGE! </em></li>

 <li><em>Run away </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> 2




<em>You surprise the dragon, wounding it greatly.  But now the dragon turns to you and prepares to scorch you with its fire breath. </em>

<em> </em>

<ol>

 <li><em>Hide behind a marble pillar </em></li>

 <li><em>Hide behind your shield </em></li>

 <li><em>Run between its legs </em></li>

</ol>

<em>Choose 1, 2, or 3:</em> 1




<em>Your cloak is a little singed, but the marble deflects most of the fire.  Wizard McBlastyFace disintegrates the dragon with a single spell. </em><strong>True </strong>