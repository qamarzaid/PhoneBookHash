### Phone Book
# work in progress....

```python


def linear(size): 		#function for linear probing

	hashL=["_"]*size
	for i in range (0,size):
		
		ele=int(input("Enter the Number: "))
		if ele>0:
			pos=ele % size
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




def Quad(size): 		#function for qaudratic probing
	
	hashQ=["_"]* size

	for i in range(0,size):
		ele=int(input("Enter Number: "))
		if ele>0:
			pos= ele%size
			if (hashQ[pos]=="_"):
				hashQ[pos]=ele
			else:
				print("Collision Occured Resolving by Quadratic Probing")

				newpos=pos
				
				i=1
				while( hashQ[newpos]!="_") :
					newpos=((pos+(i**2))%size)
					#print("newpos",newpos)
					i=i+1
				hashQ[newpos]=ele
		else:
			pass

	return hashQ

	






def display():    	#function to display
	print("---------Linear Probing----------")
	sizeL=int(input("Enter the size of hash table : "))
	lp=linear(sizeL) 		#calling linear probing function
	print(lp)
	print("---------Quadratic Probing----------")
	sizeQ=int(input("Enter size of the Hash Table: "))

	#print(Quad(sizeQ))
	#searchL(lp,sizeL)
display()
