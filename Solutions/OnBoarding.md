# Onboarding

![](https://static.codingame.com/servlet/fileservlet?id=4769224417384&format=puzzle_cover)

> Codingame is the owner of the image
>

## Objective



Solving this puzzle helps you understand how CodinGame puzzles work (input data recovery, game loop, sending results to standard output). You can discover the platform with this simple value comparison exercise and discover up to 25 programming languages 

A tutorial mission for newcomers: your program must find which of the two targets is closest. 



## Answer



### C#

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

        while (true)
        {
            string enemy1 = Console.ReadLine();
            int dist1 = int.Parse(Console.ReadLine());
            string enemy2 = Console.ReadLine();
            int dist2 = int.Parse(Console.ReadLine());
            
            if (dist1 < dist2) {
                Console.WriteLine(enemy1);
            } else {
                Console.WriteLine(enemy2);
            }
            
        }
    }
}
``````





### Java

``````Java
import java.util.*;

class Player {

    public static void main(String args[]) {
        Scanner in = new Scanner(System.in);

        while (true) {
            String enemy1 = in.next();
            int dist1 = in.nextInt();
            String enemy2 = in.next();
            int dist2 = in.nextInt();
            
            if (dist1 < dist2) {
                System.out.println(enemy1);
            } else {
                System.out.println(enemy2);
            }

        }
    }
}
``````



## Explanation

