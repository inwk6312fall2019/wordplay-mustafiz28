# wordplay-mustafiz28
wordplay-mustafiz28 created by GitHub Classroom
9.1
""" need to implement a code which will read a particular file ("words.txt) and print out the words containing more than
20 characters without any whitespace """

#mustafiz@mustafiz-VirtualBox:~/mustafiz$ nano 9_1.py

myfile = open('words.txt')
for line in myfile:
    word = line.strip()
    if len(word) > 20:				#if len(word) > 20 == True:	
        print(word)

#mustafiz@mustafiz-VirtualBox:~/mustafiz$ python3 9_1.py



9.2
""" need to write a function called has_no_e that returns True if the given word doesn’t have the letter “e” in it. then 
need to compute the percentage of the words in the file ("words.txt) having no e in it """

#mustafiz@mustafiz-VirtualBox:~/mustafiz$ nano 9_2.py

myfile = open ("words.txt")
line = myfile.readline()

def has_no_e(word):
	for char in word:
		if char  in 'Ee':
			return False
	return True

count = 0
word_number = 113809 		

for line in myfile:
	word = line.strip()
	if has_no_e(word):				#if has_no_e(word) == True:
		count +=1
		print(word)

print("word without containing e :",count)
percentage =(count/word_number)*100
print("Percentage :",percentage)

#mustafiz@mustafiz-VirtualBox:~/mustafiz$ python3 9_2.py


9.3

""" need to write a function where after tracking all the words of a file, prints out all the words not containg any particular letters based on input"""

myfile = open("words.txt")
line = myfile.readline()

def avoids(word,letter):
  word = line.strip()
  for char in word:
    if char in letter:
      return False
  return True

excluded_letter=input("input excluded letter :")
count = 0

for line in myfile:
  word = line.strip()
  if avoids(word,excluded_letter):			#if avoids(word,excluded_letter) == True:
    count+=1
    print(word)

print("count :",count)


9.4


"""need to write a function which tracks all the words of file and prints out required words which only contains particular letters"""

myfile = open ("words.txt")
line = myfile.readline()

def uses_only(word,letter):
  for char in word:
    if char not in letter:
      return False
  return True

count=0
for line in myfile:
  word = line.strip()
  if (uses_only(word,"acefhlo")):			#if (uses_only(word,"acefhlo")) == True:
    count +=1
    print(word)

print("count :",count)



9.5

"""need to write a function which prints out words containing a required set of letters from a file """


myfile = open ("words.txt")
line = myfile.readline()

def uses_all(word,letters):
  for char in letters:
    if char not in word:
      return False
  return True

count = 0
required_letters=input("required letters :")
for line in myfile:
  word = line.strip()
  if uses_all(word,required_letters):			#if uses_all(word,required_letters) == True:
    count +=1
    print(word)

print("count :",count)


9.6

"""need to write a funtion which tracks all words from a file and will print out words containing letters in a ascending order """

def is_abecedarian(word):
    previous_letter = word[0]
    for letter in word:
        if ord(letter) < ord(previous_letter):
            return False
        previous_letter = letter
    return True


myfile = open('words.txt')
line = myfile.readline()
count = 0

for line in myfile:
    word = line.strip()
    if is_abecedarian(word):		#if is_abecedarian(word) == True:
        print(word)
        count += 1

print("count :",count)


9.7

"""need to write a function which sorts out only those words containing two consecutive lettes three times from a file"""

myfile = open('words.txt')
line = myfile.readline()

def is_triple_double(word):
    count = 0
    index = 0
    while index < len(word) - 1:
        if word[index] == word[index + 1]:
            count += 1
            if count == 3:
              return True
            index += 2
        else:
            count = 0
            index += 1

total_count = 0
for line in myfile:
    word = line.strip()
    if is_triple_double(word):			#if is_triple_double(word) == True:
        print(word)
        total_count += 1

print("total count :",total_count)



9.8


def is_palindrome(word):
    return word == word[::-1]


def searched_number(number):
    if is_palindrome(str(number)[2:]):
        number += 1
        if is_palindrome(str(number)[1:]):
            number += 1
            if is_palindrome(str(number)[1:5]):
                number += 1
                if is_palindrome(str(number)):
                    return True
    return False


for num in range(100000, 1000000):
    if searched_number(num):
        print(num)





