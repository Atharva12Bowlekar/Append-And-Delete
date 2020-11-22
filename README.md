# Append-And-Delete
Append and delete is one of hackerrank's algorithm implementation problems.  (20 points)

Hello Humans!!!!

How is it going???

Let's walk through the code.

#!/bin/python3

import math

import os

import random

import re

import sys

Complete the appendAndDelete function below.

def appendAndDelete(s, t, k):
    c=0          #Set up for a counter
    for i in range(min(len(s),len(t))):     #For loop to get the number of similar characters in the strings s and t, starting from index position 0.
        if(s[i]==t[i]):
            c=c+1
        else:
            break      #Counts number of similar letters in both the strings and breaks on non-similar string characters.
    a=len(s)-c         #Gives the number of characters to be removed from string s.
    b=len(t)-c   #Gives the number of characters to be added to above variable a.
    if(k>=(a+b)):    #k(no of append and delete operations) needs to be greater than the sumation of variables a and b.
        if((a+b)==0 and len(t)<k):    #To bypass zero division error 
            return 'Yes'    
        elif(k>(len(s)+len(t))):      #If k is greater than sum of characters of string s and t
            return 'Yes'
        elif((k-(a+b))%2==0):         #To check the difference between k and the sum of variables a andd b is even, so after manipulation result string t can be obtained.
            return 'Yes'
        else:
            return 'No'
    else:
        return 'No'
if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')
    s = input()
    t = input()
    k = int(input())
    result = appendAndDelete(s, t, k)
    fptr.write(result + '\n')
    fptr.close()
 

