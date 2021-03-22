### Phone Book
# work in progress....

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


	






def display():    	#function to display
	print("---------Linear Probing----------")
	sizeL=int(input("Enter the size of hash table : "))
	lp=linear(sizeL) 		#calling linear probing function
	print(lp)
	print("---------Quadratic Probing----------")
	sizeQ=int(input("Enter size of the Hash Table: "))
	qp=Quad(sizeQ)			#calling quadratic probing function
	
display()
