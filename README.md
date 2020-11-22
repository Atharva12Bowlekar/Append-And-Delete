# Append-And-Delete
def appendAndDelete(s, t, k):
    c=0
    #Set up for a counter
    for i in range(min(len(s),len(t))):                 
    #For loop to get the number of similar characters in the strings s and t, starting from index position 0.
        if(s[i]==t[i]):
            c=c+1
        else:
            break
    #Counts number of similar letters in both the strings and breaks on non-similar string characters.

    a=len(s)-c 
    #Gives the number of characters to be removed from string s.

    b=len(t)-c
    #Gives the number of characters to be added to above variable a.

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

