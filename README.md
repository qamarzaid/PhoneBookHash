### Phone Book
# work in progress..
#### Code:
#####  Function for creating phonebook using linear probing
```python


def linear(size):
	
	hashL=["_"]*size
	for i in range (0,size):
		
		ele=(input("Enter the Number: "))
		if int(ele)>0:
			pos=int(ele) % size
			if (hashL[pos]=="_"):
				hashL[pos]=ele
			else:
				print("Collision Occured Resolving by Linear Probing")
				newpos=pos
				#print(newpos)
				i=0
				while(hashL[newpos]!="_"):
					newpos=(pos+i)%size
					i=i+1
				hashL[newpos]=ele
			#print(hashL)
		else:
			pass
	return hashL
```
#####  Function for creating phonebook using Quadratic probing
```python
def Quad(size):
	
	hashQ=["_"]* size

	for i in range(0,size):
		ele=(input("Enter Number: "))
		if int(ele)>0:
			pos= int(ele)%size
			if (hashQ[pos]=="_"):
				hashQ[pos]=ele
			else:
				print("Collision Occured Resolving by Quadratic Probing")

				newpos=pos
				
				i=1
				#newpos=((pos+(i**2))% size)
				#print("pos",pos)
				#print("newpos",newpos)
				while( hashQ[newpos]!="_") :
					newpos=((pos+(i**2))%size)
					#print("newpos",newpos)
					i=i+1
				hashQ[newpos]=ele
		else:
			pass

	return hashQ
```
##### Function for searching phone number linear probing hashtable
```python
def searchL(list, size):
	key=(input("Enter No. To search"))
	pos= int(key) %size
	count=0
	if list[pos]==key:
		count=count+1
		print (" up Contact Found At ", pos )
		print("Number of comparision Done", count)
		
	elif list[pos]!=key:
		i=0
		
		newpos=pos
		for j in range(i,size):
			count=count+1

			if list[newpos]==key:
				print("down Contact Found At ", newpos)
				print("Number of comparision Done", count)
				break
			else:
				newpos=(newpos+i)%size

				i=i+1
				#print(newpos)
				#print(i)
				if(i>=size):
					print("Contact Not Found")
					break
```
##### Function for displaying phonebook
```python
def display():
	print("---------Linear Probing----------")
	sizeL=int(input("Enter the size of hash table : "))
	lp=linear(sizeL)
	print(lp)
	#print("---------Quadratic Probing----------")
	#sizeQ=int(input("Enter size of the Hash Table: "))

	#print(Quad(sizeQ))
	searchL(lp,sizeL)
display()
```
	
##### Work in progresss....

