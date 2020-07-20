# Gate Counter

## Step 1
First, we need to create a variable to store the number of people
who are in the building. 

Test out your code with the simulator as you go (from **Step 5** onwards).

## Step 2
Go to the Variables section and **make a variable**
and call it **counter**.
You should see three new blocks appear in the **Variables** section:
- counter
- set counter to 0
- change counter by 1

## Step 3
At the start of our program there are 0 people in the building, so **set**
counter to 0 **on start**.
```blocks
let counter = 0;
```

## Step 4
We are going to use the A and B buttons to add to and subtract from the gate
counter, by **changing** the variable.
When someone who is at the gate sees someone go in they press A and when someone
leaves they press B.
Drag in **on Button A press** from **Input** and use that to change the variable.
Then do the same for B button.
```blocks
input.onButtonPressed(Button.A, function () {
    counter += 1;
})
input.onButtonPressed(Button.B, function () {
    counter += -1;
})
```

## Step 5
We want to be able to see how many people are in the building by pressing
A and B together.
Use the **show number** block from **Basic** together with the **counter** block from
**Variables** to see how many people are inside.

```blocks
input.onButtonPressed(Button.AB, function () {
    basic.showNumber(counter)
})
```

## Step 6
Now let's get some hints on the screen for what buttons you pressed.
From the **Basic** section, add a **show arrow West** block to the A button
and a **show arrow East** block to the B button.

```blocks
input.onButtonPressed(Button.A, function () {
    counter += 1
    basic.showArrow(ArrowNames.West)
})
```

## Step 7
What happens if you keep pressing the B button? Your number of people can
go into the negatives! That doesn't make any sense, so let's add an **if**
block from the **Logic** section, replace the **true** hexagon with an **=**
block from the **Logic** section (then change the symbol to **>** for greater than)
and lastly put a **counter** block on the left side, so that we only subtract
a person if there are more than 0 people inside.

```blocks
input.onButtonPressed(Button.B, function () {
    if (counter > 0) {
        counter += -1
        basic.showArrow(ArrowNames.East)
    }
})
```

## Step 8
You're done!

Try it out in the simulator, and then download it to a Micro:bit and make
sure it works on the real thing.

Check out the extension problems in OneNote if you have time.
