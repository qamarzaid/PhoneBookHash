### Phone Book

```python


def linear(size):
	#print("---------Linear Probing----------")
	#size=int(input("Enter the size of hash table : "))
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

#linear()



def Quad(size):
	
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

	






def display():
	print("---------Linear Probing----------")
	sizeL=int(input("Enter the size of hash table : "))
	lp=linear(sizeL)
	print(lp)
	#print("---------Quadratic Probing----------")
	#sizeQ=int(input("Enter size of the Hash Table: "))

	#print(Quad(sizeQ))
	#searchL(lp,sizeL)
display()
