# POWER OF THOR - EPISODE 1

![](https://static.codingame.com/servlet/fileservlet?id=5690532126778&format=puzzle_cover)

> Codingame is the owner of the image

## Objective

> Difficulty: **Easy**

A basic problem to go a step further with the conditions and variables: your program must allow Thor to join the coordinates of the flash of power in a field in 2D.

Thor's hammer, Mjöllnir, has lost all power ... Will you be able to guide Thor to the lightning of power to restore his strength to the hammer? 



## Answer



``````C#
using System;
using System.Linq;
using System.IO;
using System.Text;
using System.Collections;
using System.Collections.Generic;

class Player
{
    static void Main(string[] args)
    {
        string[] inputs = Console.ReadLine().Split(' ');
        int lightX = int.Parse(inputs[0]);
        int lightY = int.Parse(inputs[1]);
        int initialTx = int.Parse(inputs[2]);
        int initialTy = int.Parse(inputs[3]);

        while (true)
        {
            int remainingTurns = int.Parse(Console.ReadLine());
            string direction = "";
            
            if(lightY > initialTy){
                direction = "S";
                initialTy++;
            }
            else if(lightY < initialTy){
                direction = "N";
                initialTy--;
            }
            
            if(lightX > initialTx){
                direction += "E";
                initialTx++;
            }
            else if(lightX < initialTx){
                direction += "W";
                initialTx--;
            }
            Console.WriteLine(direction);
        }
    }
}
``````



## Explanation

