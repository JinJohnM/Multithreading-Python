# Multithreading-Python
User input numbers of row then the program will do a row sum simultaneously.
import time as ti
import threading

def rowsum(a):
    for i in range(inp):
        k.append(sum(inarray))
        
def double1(a):
    for i in range(int(inp/2)):
        k.append(sum(inarray))
def double2(a):
    for i in range(int(inp/2),inp,1):
        k.append(sum(inarray))

def four1(a):
    for i in range(0,int(len(a)/4),1):
        k.append(sum(a[i]))
def four2(a):
    for i in range(int(len(a)/4),int(len(a)/4)+1,1):
        k.append(sum(a[i]))
def four3(a):
    for i in range(int(len(a)/4)+1,int(len(a)/4)+3,1):
        k.append(sum(a[i]))
def four4(a):
    for i in range(int(len(a)/4)+3,int(len(a)),1):
        k.append(sum(a[i]))

def eight1(a):
    Sum1=0
    for i in range(1000000):
        Sum1=Sum1+1
    Sum=Sum1
    k.append(Sum)
def eight2(a):
    Sum1=0
    for i in range(1000000):
        Sum1=Sum1+1
    Sum=Sum1
    k.append(Sum)
def eight3(a):
    Sum1=0
    for i in range(1000000):
        Sum1=Sum1+1
    Sum=Sum1
    k.append(Sum)
def eight4(a):
    Sum1=0
    for i in range(1000000):
        Sum1=Sum1+1
    Sum=Sum1
    k.append(Sum)
def eight5(a):
    Sum1=0
    for i in range(1000000):
        Sum1=Sum1+1
    Sum=Sum1
    k.append(Sum)
def eight6(a):
    Sum1=0
    for i in range(1000000):
        Sum1=Sum1+1
    Sum=Sum1
    k.append(Sum)
def eight7(a):
    Sum1=0
    for i in range(1000000):
        Sum1=Sum1+1
    Sum=Sum1
    k.append(Sum)
def eight8(a):
    Sum1=0
    for i in range(1000000):
        Sum1=Sum1+1
    Sum=Sum1
    k.append(Sum)

Sum=0
Sum1=0
Sum2=0
k=[]
                                  
inp=int(input("Number of rows: "))
inarray = [1]*1000000
array = [inarray]*inp 

print()
print("Array size",end=' ')
print(inp,end='X')
print("1000000")
print("----- No Threading -----")
count=1
for i in range(12):
    print("t = ",count)
    time=ti.time()
    rowsum(array) 
    print("Done in: ", (ti.time()-time)*1000," ms")
    count=count+1
    print(k)
    del k[:]

print()
print("Array size",end=' ')
print(inp,end='X')
print("1000000")
print("----- Double Threading -----")
count=1
for i in range(12):
    print("t = ",count)
    time=ti.time()
    t1=threading.Thread(target=double1,args=(array,))
    t2=threading.Thread(target=double2,args=(array,))
    t1.start()
    t2.start()
    t1.join()
    t2.join()
    print("Done in: ", (ti.time()-time)*1000," ms")
    count=count+1
    print(k)
    del k[:]

print()
print("Array size",end=' ')
print(inp,end='X')
print("1000000")
print("----- Fourth Threading -----")
count=1
for i in range(12):
    print("t = ",count)
    time=ti.time()
    t1=threading.Thread(target=four1,args=(array,))
    t2=threading.Thread(target=four2,args=(array,))
    t3=threading.Thread(target=four3,args=(array,))
    t4=threading.Thread(target=four4,args=(array,))
    t1.start()
    t2.start()
    t3.start()
    t4.start()
    t1.join()
    t2.join()
    t3.join()
    t4.join()
    print("Done in: ", (ti.time()-time)*1000," ms")
    count=count+1
    print(k)
    del k[:]

print()
print("Array size",end=' ')
print(inp,end='X')
print("1000000")
print("----- Eighth Threading -----")
count=1
for i in range(12):
    print("t = ",count)
    time=ti.time()
    t1=threading.Thread(target=eight1,args=(array,))
    t2=threading.Thread(target=eight2,args=(array,))
    t3=threading.Thread(target=eight3,args=(array,))
    t4=threading.Thread(target=eight4,args=(array,))
    if len(array)>4:
        t5=threading.Thread(target=eight5,args=(array,))
        t6=threading.Thread(target=eight6,args=(array,))
        t7=threading.Thread(target=eight7,args=(array,))
        t8=threading.Thread(target=eight8,args=(array,))
    t1.start()
    t2.start()
    t3.start()
    t4.start()
    if len(array)>4:
        t5.start()
        t6.start()
        t7.start()
        t8.start()
    t1.join()
    t2.join()
    t3.join()
    t4.join()
    if len(array)>4:
        t5.join()
        t6.join()
        t7.join()
        t8.join()
    print("Done in: ", (ti.time()-time)*1000," ms")
    count=count+1
    print(k)
    del k[:]
