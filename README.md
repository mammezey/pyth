# pyth
# Python Program to return a list or the largest integer
# By mohammed Endris
#######################################################

def GetAvIncome(income):			#Function to Calculate Average income
	tot=sum(income.values())
	return float(tot)/float(len(income.values()))

	
def DictionFormat(item):		# Function to format the Dictionary
	print "| Name			|  Salary |"
	print "-" * 35
	for i,j in item.iteritems():
		print "| %-21s | %7d |" %(i,j)
		print "-" * 35

		
def ReadEntry(name,d):		#Reading entries in the Dictionary
	if d.has_key(name):
		Tempo=[name,d[name]]
		return Tempo
	else:
		print "This name is not included in the list:  "
		return -1

		
def AttachSalary(name,amt,dn):		#Attach Salary to a person in the dictionary
	if dn.__contains__(name):
		dn[name]+=amt
		return dn
	else: 
		print "This name is not included in the list:  "
		return dn

		
def PutInEntry(name,sal,dn):		#Adding entries
	if dn.__contains__(name):
		print "Entry already Exists in Dictionary:  "
		return dn
	else:
		dn[name]=sal
		return dn

		
size=int(raw_input(" Enter the number of items in the Dictionary: "))
name=[]
salary=[]
i,Tempo=0,0
nameS=[]
d=dict()   #The dictionary listing Name with Salary
D1=dict()
for i in range(0,size):
	name.append(raw_input("Enter Name:  "))
	salary.append(int(raw_input("Enter corresponding Salary:  ")))
print salary
print name


# Name-Salary listing Dictionary
index, Tempo=0,0
for v,c in zip(name,salary):
	D1[v]=c
	
	
#print "dictionary 1 is: ",d
print "dictionary 2 is: "
DictionFormat(D1)
print "Average Salary = ", GetAvIncome(D1)
nom=raw_input("Enter a new name:")
Salry=int(raw_input("Enter its salary "))
print "The  dictionary after a new addition is: ", addEntry(nom,Salry,D1)
nom2=raw_input("Enter an entry to find: ")
print "The entry in the Dictionary is : ",ReadEntry(nom2,D1)
