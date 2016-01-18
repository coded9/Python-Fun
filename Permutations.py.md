#Take a string as an input and store all the permutations in a file

##The library way

```
from itertools import permutations
word = raw_input("Enter the word:")
fname = raw_input("Enter the file name(ending with .txt ):")
perms = [''.join(p) for p in permutations(word)]
file = open(fname,"w")
for perm in perms:
  file.write(perm+"\n")

```  
  
##The programmer way

```
word = raw_input("Enter the word:")
fname = raw_input("Enter the file name(ending with .txt ):")
def permutations(word):
    if len(word)<=1:
        return [word]

    #get all permutations of length N-1
    perms=permutations(word[1:])
    char=word[0]
    result=[]
    #iterate over all permutations of length N-1
    for perm in perms:
        #insert the character into every possible location
        for i in range(len(perm)+1):
            result.append(perm[:i] + char + perm[i:])
    return result
perms = permutations(word)
file = open(fname,"w")
for wordd in perms:
  file.write(wordd+"\n")
```
