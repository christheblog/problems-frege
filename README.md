# Problems-Frege


## Description

This project will contains some small problems that I enjoyed solving in Frege. 
It will be most likely short snippets of code 

Frege is a Haskell for the JVM. If you are interested you can have a look at the following links : 
https://github.com/Frege/frege/wiki/_pages
https://github.com/Frege/frege 

Frege also has a simple Eclipse plugin available here : https://github.com/Frege/eclipse-plugin/wiki/fregIDE-Tutorial 


## Towers Of Hanoi

If you don't know what this puzzle is about, you can have a look at the Wikipedia page : https://en.wikipedia.org/wiki/Tower_of_Hanoi

A short description of the puzzle is : 

The puzzle consists of three rods, and a number of rings of different sizes which can slide and stack-up onto any rod.
The initial state of the puzzle is a pile of rings stacked in ascending order on one of the rods.

The objective of the puzzle is to move all the rings to another rod, using the following rules :
- Only one ring can move at a time.
- Only an upper ring can be taken
- A move consists of moving the upper ring from one of rod and put it at the top of the stack of another rod.
- A Ring cannot be placed on the top of a smaller one 


The solution implemented is a recursive algorithm to move the tower from the first rod to the second or third rod.

The following type aliases have been declared :
```
-- A tower is an ascending ordered list of rings
-- Towers is a 3-uplet of Tower
type Ring = Int
type Tower = [Ring]
type Towers = (Tower,Tower,Tower)
-- When moving a token from a source to a destination 
type Src = Int
type Dest = Int
type Move = (Src,Dest)
-- Ring depth level
type Depth = Int 
```

Creating a new puzzle of n disks on rod 1 is done by calling the create function :
```create :: Depth -> Towers```

Solving the problem is actually done by calling the `move` function declared as follow :
```move :: Depth -> Move -> State Towers ()```

The call `move 4 (1,3)` means : `move 4 rings from tower 1 onto tower 3`



