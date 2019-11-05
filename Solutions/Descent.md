# The Descent

![](https://static.codingame.com/servlet/fileservlet?id=4769420985292&format=puzzle_cover)

> Codingame is the owner of the image

[**Original Link**]( https://www.codingame.com/training/easy/the-descent )

## Objective

> Difficulty: **Easy**

A simple problem to experience the CodinGame platform: your program must find the highest mountain among a list of mountains. 

The Enterprise vessel is in danger: lured down, it is likely to crash into the mountains of an unknown planet. Help Kirk and Spock destroy the mountains ... save the Enterprise! 



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
        int Hmountain = 0;
        int hit = 0;
            for (int i = 0; i < 8; i++)
            {
                int mountainH = int.Parse(Console.ReadLine());
                if(Hmountain < mountainH){
                    Hmountain = mountainH;
                    hit = i;
                }
            }
            Console.WriteLine(hit); 

        }
    }
}
``````





### Java

``````Java
import java.util.*;
import java.io.*;
import java.math.*;

class Player {

    public static void main(String args[]) {
        Scanner in = new Scanner(System.in);
        while (true) {
        int Hmountain = 0;
        int hit = 0;
            for (int i = 0; i < 8; i++) {
                int mountainH = in.nextInt();
                if (Hmountain < mountainH) {
                    Hmountain = mountainH;
                    hit = i;
                }     
            }
            System.out.println(hit);
        }
    }
}
``````



## Explanation

