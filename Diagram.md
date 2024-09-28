```mermaid

flowchart TD

    Start[Start]-->st1([#quot;I'm going to think of a number between 0 and 99. Can you guess what number I'm thinking of?#quot;]);
    st1--Enter-->st1.1[Generate a random number within that range];
    st1.1-->st2[Ask for user input];
    st2--User inputs their guess-->st3[Sanitize user input to make sure it's nothing but any two numerical digits];
    st3--If user inputs something other than a number between 0 and 99-->st3.1{#quot;Please choose a number between 0 and 99#quot;};
    st3.1-->st2;
    st3--If input matches the requirements-->st4[Compare user input to the random number];
    st4--If the guess is lower than the random number-->lower([#quot;The number you guessed was lower than the target#quot;]);
    st4--If the guess is higher than the random number-->higher([#quot;The number you guessed was higher than the target#quot;]);
    st4--If the user guessed the number correctly-->correct([#quot;Good job! You guessed the number correctly#quot;]);
    lower-->repeat([#quot;Would you like to go again?#quot;]);
    higher-->repeat;
    correct-->repeat;
    repeat--If yes-->st1;
    repeat--If no -->stop([#quot;Thank you!#quot;]);
    stop-->End[End];

```

# Documentation

## Start

The start node occurs when we launch the program. It immediately proceeds to the next node.

## Greeting

This node prints a message to greet the user, and defines the rules of the game. When the user presses enter the program proceeds to the next step.

## Generate a random number

At this step the program generates a random number between 0 and 99, then immediately proceeds to the next step. 

## Ask the user for input

At this node, the user is prompted for their input. After the input is recieved the program proceeds to the next step. 

## Sanitize the input

At this node, the program checks the user's input to make sure it is a number between 0 and 99. If it is not, it sends the user back to the node that accepts their input to try again.  
If the  input is acceptable, it proceeds to the next node. 

## Verify the guess

At this node, the program compares the user's input to the randomly generated number. It sends the user to one of three possible nodes, depending on whether the guess was higher, lower, or exactly the same as the randomly generated number. All three of these nodes tell the user how they did and then proceed to the same node.

## Ask if the user wants to play again

The next node asks the user if they would like to try the guessing game again. If they input yes, the program goes back to the Greeting node. If the user inputs no, the program prints "Thank you!" and ends.
