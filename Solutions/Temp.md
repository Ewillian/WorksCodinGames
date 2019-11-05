# Temperatures

![](https://static.codingame.com/servlet/fileservlet?id=4768860147383&format=puzzle_cover)

> Codingame is the owner of the image
>

[**Original Link**]( https://www.codingame.com/training/easy/temperatures )

## Objective

> Difficulty: **Easy**

Your program must analyze temperature readings to find the closest to zero. It's cold ! Can you find the temperature closest to zero in a temperature reading? 



## Answer



``````C#
using System;
using System.Linq;
using System.IO;
using System.Text;
using System.Collections;
using System.Collections.Generic;

class Solution
{
    static void Main(string[] args)
    {
        int n = int.Parse(Console.ReadLine());
        int result = 0;
        int pos = 0;
        int posresult = 5527;
        string[] inputs = Console.ReadLine().Split(' ');
        for (int i = 0; i < n; i++)
        {
            int t = int.Parse(inputs[i]);
            if(t < 0){
                pos = t*(-1);
            }
            else{
                pos = t;
            }
            if(pos < posresult){
                result = t;
                posresult = pos;
            }
            else if(pos == posresult){
                if(t > result){
                    result = t;
                }
            }
        }
        Console.WriteLine(result);
    }
}
``````



## Explanation

