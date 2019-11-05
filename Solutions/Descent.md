















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

