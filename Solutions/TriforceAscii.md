# MAY THE TRIFORCE BE WITH YOU!

![](https://d.facdn.net/art/thelonelywolf/1488278723/1342350392.thelonelywolf_ascii-link_artwork_2__the_minish_cap_.gif)

[Original link](https://www.codingame.com/training/easy/may-the-triforce-be-with-you)

## Objective

> Difficulty: **Easy**

Link has been sent to the Secret Realm to find the Triforce and save Hyrule. But the vile Ganondorf followed Link into the Temple of Time, trapped him, and took the Triforce for himself.
The Temple of Time has been closed for a thousand years now, but the Sages finally found you, one of the greatest Nerds ever born, and they need your help to open the Temple of Time's door and join Link in the ultimate battle!

**The program**
You must create a program that echoes a Triforce of a given size `N`.

- A Triforce is made of 3 identical triangles.
- A triangle of size `N` should be made of `N` lines.
- A triangle's line starts from 1 star, and earns 2 stars each line.
- Take care, a `.` must be located at the top/left to avoid automatic trimming.  

For example, a Triforce of size 3 will look like:

```
.    *
    ***
   ***** 
  *     * 
 ***   ***
***** *****
```

```

.        *
        ***
       ***** 
      *******
     *********
    *         * 
   ***       ***
  *****     *****
 *******   *******
********* *********

```

Don't forget: you're Hyrule's only hope!
Good luck! 



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
        int N = int.Parse(Console.ReadLine());
        int spaces = (N * 2) - 2;
        int spaces2 = (N * 2) - 1;
        int stars = 3;
        int stars2 = 1;
        string firstLine = ".";

        List<string> body = new List<string>();
        
        //First line with dot
        for (int i = 0; i < spaces; i++){
            firstLine += " ";
        }
        firstLine += "*";
        body.Add(firstLine);

        //Constructing TriForce
        for (int i = 1; i < (N * 2); i++){
            string content = "";
            int count = 0;
            
            //Constructing first Force from line 2
            if(i < N && spaces >=N){
                //Spaces
                for (int lineContent = 1; lineContent <= spaces; lineContent++){
                    content+=" ";
                }
                //Stars
                for (int starcount = 0; starcount < stars; starcount++){
                    content+="*";
                }
                stars += 2;
            }
            
            // Constructing second and third Forces
            else{
                //Spaces
                for (int lineContent = 0; lineContent < spaces; lineContent++){
                    content+=" ";
                }
                //Stars
                for (int lineContent = 0; lineContent < stars2; lineContent++){
                    content+="*";
                }
                //Spaces
                for (int lineContent = 0; lineContent < spaces2; lineContent++){
                    content+=" ";
                }
                //Stars
                for (int lineContent = 0; lineContent < stars2; lineContent++){
                    content+="*";
                }
                stars2 += 2;
                spaces2 -= 2;
            }
            spaces--;
            body.Add(content);
        }
        
        //return
        foreach (string s in body){
            Console.WriteLine(s);
        }
    }
}
``````



## Explanation

