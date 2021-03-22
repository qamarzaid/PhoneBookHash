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



	






def display():    	#function to display
	print("---------Linear Probing----------")
	sizeL=int(input("Enter the size of hash table : "))
	lp=linear(sizeL) 		#calling linear probing function
	print(lp)
	print("---------Quadratic Probing----------")
	sizeQ=int(input("Enter size of the Hash Table: "))
	qp=Quad(sizeQ)			#calling quadratic probing function
	
display()
