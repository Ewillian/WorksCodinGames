# Chuck Norris

[Original link]( https://www.codingame.com/training/easy/chuck-norris )

## Objective

> Difficulty: **Easy**

Your program must turn a string into a series of zeros. A string also has an encrypted form and you must transform that form into another format. 

The binary is good! But the unary is better! Put your encoding skills to the test in this challenge where you will have to transform messages into "unary" (0 00 000 0 ...). 



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
class Solution {
	static void Main(string[] args)
        {
            string MESSAGE = Console.ReadLine();
            string binary = "";
            string unary = string.Empty;
            foreach (char m in MESSAGE)
            {
                //To binary
                string mylength = Convert.ToString((int)m, 2);
                //if length is not 7bytes
                if (mylength.Length < 7)
                {
                    mylength = new string('0', 7- mylength.Length) + mylength;
                }
                binary += mylength;
            }
            
            char[] binaryArray = binary.ToArray();
            string result = "";
            char lastChar = '\0';
            
            for (int i = 0; i<binaryArray.Length; i++)
            {
                char currentchar = binaryArray[i];
                if (lastChar != '1' && currentchar == '1')
                {
                    result += " 0 0";
                    lastChar = '1';
                }
                else if (lastChar == '1' && currentchar == '1')
                {
                    result += "0";
                }
                else if (lastChar != '0' && currentchar == '0')
                {
                    result += " 00 0";
                    lastChar = '0';
                }
                else if (lastChar == '0' && currentchar == '0')
                {
                    result += "0";
                }
                else
                {
                    result += "error";
                }
             }
            
            Console.WriteLine(result.Trim());
        }
}
``````



## Explanation

