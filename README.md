
"""
    Docstrings Indicate an action from the user, acting as instructions
    Hashes explain what the code further for anybody working with the code
"""
import random


#Function that replaces all empty spaces with a random letter
def randomFill(wordsearch):
  LETTERS="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
  for row in range(0,a):
    for col in range(0,b):
      if wordsearch[row][col]=="-":
        randomLetter = random.choice(LETTERS)
        wordsearch[row][col]=randomLetter

a = 16
#sets the row length
b = 16
#sets the column width
b2 = b*2+1
#sets the top of the box
b3 = b*2-1
#sets the bottom of the box

#sets list for random 
L = list(range(0,a))


#Function that prints wordseatch onto console
def displayWordsearch(wordsearch):
  print("","_"*int(b2))
  for row in range(0,a):
    line="| "
    for col in range(0,b):
      line = line + wordsearch[row][col] + " "
    line = line + "|"
    print(line)
  print("|","_"*int(b3),"|")  

#Creates wordsearch block
wordsearch = []
for row in range(0,a):
  wordsearch.append([])
  for col in range(0,b):
    wordsearch[row].append("-")
    
    
#Function that adds words to wordsearch block randomly
def addWord(word,wordsearch):
    c = len(word)
    row=random.randint(0,a)
    while row not in L:
        row=random.randint(0,a)
        if row in L:
            L.pop(row)
    col=random.randint(0,b-c)
    for i in range(0,len(word)):
        wordsearch[row][col+i]=word[i]
"""
  Type desired words for wordearch between quotation marks
  limit length of words to row length (variable a)
"""
#allows user to insert words into wordsearch
addWord("PYTHON",wordsearch)    
addWord("ALGORITHM",wordsearch)    
addWord("CODING",wordsearch)    
addWord("PROGRAM",wordsearch)
addWord("FINDER",wordsearch)  

randomFill(wordsearch)

#Spaces not filled with letter in word given will be given a random letter to take its place


#Displays the completed wordsearch on console
displayWordsearch(wordsearch)
"""
    Type added words into my list
    Add one word between each set of quotation marks 
"""
#creates word bank for wordsearch so user knows what to look for on other side
def createwordbank():
    
  mylist = ["Python","Algorithm","Coding","Program", "Finder"]
  for i in range(20): 
      mylist.append(i)
      return mylist
#displays word bank on console
print(createwordbank())
