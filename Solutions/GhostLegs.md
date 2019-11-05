# Ghost Leg

![](https://static.codingame.com/servlet/fileservlet?id=31874781885365&format=puzzle_cover)

> Codingame is the owner of the image
>

[Original link]( https://www.codingame.com/training/easy/ghost-legs )

## Objective

> Difficulty: **Easy**

Ghost Legs is a kind of lottery game common in Asia. It starts with a number of vertical lines. Between the lines there are random horizontal connectors binding all lines into a connected diagram, like the one below.

``````
A  B  C
|  |  |
|--|  |
|  |--|
|  |--|
|  |  |
1  2  3
``````

To play the game, a player chooses a line in the top and follow it downwards. When a horizontal connector is encountered, he must follow the connector to turn to another vertical line and continue downwards. Repeat this until reaching the bottom of the diagram.

In the example diagram, when you start from A, you will end up in 2. Starting from B will end up in 1. Starting from C will end up in 3. It is guaranteed that every top label will map to a unique bottom label.

Given a Ghost Legs diagram, find out which top label is connected with which bottom label. List all connected pairs.



## Answer



``````C#
using System;
using System.Linq;
using System.IO;
using System.Text;
using System.Collections;
using System.Collections.Generic;

/**
 * Auto-generated code below aims at helping you parse
 * the standard input according to the problem statement.
 **/
class Solution
{
    static void Main(string[] args)
    {
        string[] line = Console.ReadLine().Split();
        int W = int.Parse(line[0]);
        int H = int.Parse(line[1]);
        
        //All the Lists
        List<string> top = new List<string>();
        List<string> bottom = new List<string>();
        
        //Get top labels
        top.AddRange(Console.ReadLine().Split(new [] { "  " }, StringSplitOptions.None));
        int[] indice = new int[top.Count];
        for (int i = 0; i < top.Count; i++)
        {
            indice[i] = i;
        }
        
        //lines
        for (int i = 0; i < H-2; i++)
        {
            line = Console.ReadLine().Split('|');
            
            //Columns
            for (int j = 0; j < line.Length; j++)
            {
                if (line[j] == "--")
                {
                    //Ajust position with indice and k
                    //indice can be see as part of coordinate
                    for (int k = 0; k < indice.Length; k++)
                    {
                        if (indice[k] == j - 1)
                        {
                            indice[k] += 1;
                        }
                        else if (indice[k] == j)
                        {
                            indice[k] -= 1;
                        }
                    }
                }
            }
        }
        //Get bot labels
        bottom.AddRange(Console.ReadLine().Split(new [] { "  " }, StringSplitOptions.None));

        //Result
        for (int z = 0; z < top.Count; z++)
        {
            Console.WriteLine(top[z] + bottom[indice[z]]);
        }
    }
}
``````



## Explanation 

