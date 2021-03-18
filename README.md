### Phone Book

```python
class HashingDemo:
		def __init__ (self):
			self.size= int(input("Enter the Size of the Hash table: "))
			self.Hash=list(0 for i in range(self.size))
			self.num=0
			self.comp=0

		def isTableFull(self):
			if self.num==self.size:
				return True
			else:
				return False

		def HashFun(self,element):
			return element%self.size

		def InsertElement_linear(self, element):
			if self.isTableFull():
				print("Hash Table Full")
				return False
			ostatus=False
			pos=self.HashFun(element)

			if self.Hashtable[pos]==0:
				self.Hashtable[pos]= element
				print("Telephone Number "+ str(element)+ "at position "+ str(pos))
				ostatus= True
				self.num+=1
			else:
				print("Collision has occured for Telephone Number "+ str(element) + "at position "+ str(pos))
				pos=self.LinearProb(element,pos)
				self.Hashtable[pos]=element
				ostatus=True
				self.num+=1
			return ostatus

		def LinearProb(self,element, position):
			while self.Hashtable[pos]!=0:
				pos+=1
				if pos>=self.size:
					pos=0
			return pos

		def InsertElement_Quad(self,element):
			if self.isTableFull():
				print("Hash Table Full")
				return False
			ostatus=False
			pos=self.HashFun(element)

			if self.Hashtable[pos]==0:
				self.Hashtable[pos]= element
				print("Telephone Number "+ str(element)+ "at position "+ str(pos))
				ostatus= True
				self.num+=1
			else:
				print("Collision has occured for Telephone Number "+ str(element)+ "at position "+ str(pos))
				ostatus,pos=self.QuadProb(element,pos) ###
				if ostatus:
					self.Hashtable[pos]=element
					self.num+=1
				self.Hashtable[pos]=element
				ostatus=True
				self.num+=1
			return ostatus

		def QuadProb (self,element,pos):
			found=False
			limit=50
			i=1
			while i<=limit:
				newpos=pos+(i**2)
				newpos=newpos%self.size
				if self.Hashtable[newpos]==0:
					found=True
					break
				else:
					i+=1
			return found,newpos
					

		def search(self,element):
			found=False
			pos=self.HashFun(element)
			self.comp+=1
			if(self.Hashtable[pos]==element):
				return pos
				isFound= True
			else:
				temp=pos-1
				while pos<self.size:
					if self.Hashtable[pos] !=element:
						pos+=1
						self.comp+=1
					else:
						return pos

				pos=temp
				while pos>=0:
					if self.Hashtable[pos]!=element:
						pos-=1
						self.comp+=1
					else:
						return pos
			if not found:
				print("Element not Found")
				return False

		def display(self):
			print("\n")
			print("----------------------------------------------")
			print("\n Position \t Telephone Number\n")
			print("----------------------------------------------")
			for i in range(self.size):
				print("\t" + str(i)+"===> "+str(self.Hashtable[i]))



h1=HashingDemo()
print("\n Inserting the telephone numbers in the table....\n")
print("\n Collision Resolution using Linear Probing\n")
h1.InsertElement_linear(1111111111)
h1.InsertElement_linear(1111111112)
h1.InsertElement_linear(1111111123)
h1.InsertElement_linear(1111111234)
h1.InsertElement_linear(1111112345)
h1.InsertElement_linear(1111123456)
h1.InsertElement_linear(1111234567)
h1.InsertElement_linear(1112345678)

h1.display()
print()
print("The Position of the number 1111234567 is :"+ str(h1.search(1111234567)))
print("The Position of the number 1111111123 is :"+ str(h1.search(1111111123)))
print("The Position of the number 1111123456 is :"+ str(h1.search(1111123456)))
print("\n------------------------------------------------------")
print("\n Total number of comparison done for searching ="+str(h1.comp))
print("\n------------------------------------------------------")
print("\n\n\n**************************************************\n")







```
