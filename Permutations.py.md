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
  
