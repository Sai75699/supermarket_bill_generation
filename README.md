# supermarket_bill_generation
from datetime import datetime
name =input("Enter your name:")
#LIST of items
lists='''
sugar   Rs 30/kg
Rice    Rs 50/kg
Salt    Rs 20/kg
Oil     Rs 100/liter
Paneer  Rs 120/kg
Maggie  Rs 50/kg
Boost   Rs 20/each
Colgate Rs 30/each


''' 
#declaration
price=0
pricelist=[]
totalprice=0
finalprice=0
ilist=[]
qlist=[]
plist=[]
#rates for items
items={'rice':50,'sugar':30,'salt':20,'oil':100,'paneer':120,'maggie':50,'boost':20,'colgate':30}

option=int(input("for list of items press 1:"))
if option==1:
    print(lists)
for i in range(len(items)):
    inp1=int(input("if you want to buy press 1 or 2 for exit"))
    if inp1==2:
        break
    if inp1==1:
        item=input("enter your items:")
        quantity=int(input("enter quantity:"))
        if item in items.keys():
            price=quantity*items[item]
            pricelist.append((item,quantity,items,price))
            totalprice+=price
            ilist.append(item)
            qlist.append(quantity)
            plist.append(price)
            gst=(totalprice*5)/100
            finalprice=gst+totalprice
        else:
            print("sorry you have entered an item which is not available")   
    else:
        print("you have entered wrong number")
    inp=input("can i bill your items yes or no:")
    if inp=='yes':
        pass
        if finalprice!=0:
            print(25*"=","sai supermarket",25*"=")
            print(28*" ","Dasarlapally")
            print("Name:",name,30*" ","Date:",datetime.now())
            print(75*"-")
            print("sno",8*" ","items",8*" ","Quantity",8*" ","price")
            for i in range(len(pricelist)):
                print(i,6*" ",4*" ",ilist[i],7*" ",qlist[i],14*" ",plist[i])
            print(75*"-")
            print(50*" ","Totalprice:","Rs",totalprice)
            print("gst amount",50*" ","Rs",gst)
            print(75*"-")
            print(50*" ","finalprice:","Rs",finalprice)
            print(75*"-")
            print(25*" ","Thanks for visiting")
            print(75*"-")
