
class Word(object):
    def __init__(self, string, index):
        self.string = string
        self.index = index
 
def createDupArray(string, size):
    dupArray = []
 
    for i in range(0,size):
        dupArray.append(Word(string[i], i))
 
    return dupArray
 
def printAnagramsTogether(wordArr, size):
    dupArray = createDupArray(wordArr, size)
 
    for i in range(0,size):
        dupArray[i].string = ''.join(sorted(dupArray[i].string))
 
 
    dupArray = sorted(dupArray, key = lambda k: k.string)
 
    for word in dupArray:
        print(wordArr[word.index],end=" ")
 
# Driver program
wordArr = [] 

n = int(input("Enter number of elements : "))   
for i in range(0, n): 
    ele =input("Enter string")
    wordArr.append(ele) 
  
size = n     
printAnagramsTogether(wordArr, size)
print(wordArr)
