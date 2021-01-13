"""
@author: Radhika
"""

import random


def insert(arr,n,m,ht):
    p=0
    for i in range (n):
        u=arr[i]%m
        if ht[u]==None:
            ht[u]=arr[i]
            
        else:
            p+=1
            for j in range (m):
                r=(u+j**2)%m
                if ht[r]==None or ht[r]=="AAAAAAAAAAAAAAAAAAAAAAAAA":
                    ht[r]=arr[i]
                    
                    break
                else:
                    p+=1
    return ht,p

def delete(arr,n,m,ht):
    p=0
    not_pres=0
    pres=0
    for i in range (n):
        u=arr[i]%m
        if ht[u]==arr[i]:
            ht[u]="AAAAAAAAAAAAAAAAAAAAAAAAA"
            pres+=1
            
        else:
            p+=1
            for j in range (m):
                r=(u+j**2)%m
                if ht[r]==arr[i]:
                    ht[r]="AAAAAAAAAAAAAAAAAAAAAAAAA"
                    pres+=1
                    break
                elif ht[r]==None:
                    not_pres +=1
                    break
                else:
                    p+=1
    return ht,p,not_pres,pres


def search(arr,n,m,ht):
    p=0
    not_pres=0
    pres=0
    index=[]
    for i in range (n):
        tb=0
        tomb=0
        u=arr[i]%m
        if ht[u]==arr[i]:
            index.append(u)
            pres+=1
            
        else:
            p+=1
            for j in range (m):
                r=(u+j**2)%m
                if ht[r]==arr[i]:
                    if tb==1:
                        index.append(tomb)
                        ht[r]=None
                        ht[tb]=arr[i]
                    else:
                        index.append(r)
                        pres+=1
                        break
                elif ht[r]==None:
                    not_pres +=1
                    index.append(None)
                    break
                elif ht[r]=="AAAAAAAAAAAAAAAAAAAAAAAAA" :
                    tb+=1
                    if tb==1:
                        tomb=r
                    p+=1
                else:
                    p+=1
                    
    return ht,p,not_pres,pres,index

n=1000000
m=(n*4)//3
alpha=0.75
print("for Quadratic Probing \n with load factor:"+str(alpha)+"\n no. slots in hash table: "+str(m))
arr=[]
for i in range(0,n):
    x= random.randint(1,n)
    arr.append(x)

ht=[None]*m                
htt,pp= insert(arr,n,m,ht)
print("\n average no. of collisons for inseting "+str(n)+ " elements: "+str(pp//n))
 

n_d=200
arr_d=[]
for i in range(0,n_d):
    x_d= random.randint(1,n)
    arr_d.append(x_d)
               
ht_d,p_d,notpresent,present= delete(arr_d,n_d,m,ht)
print("\n average no. of collisons for deleting "+str(n_d)+ " elements: "+str(p_d/n))
print("\n no. of succesful deletion: "+str(present)+"\n no. of unsuccesful deletion: " +str(notpresent))       
           
n_d=200
arr_d=[]
for i in range(0,n_d):
    x_d= random.randint(1,n)
    arr_d.append(x_d)
               
ht_d,p_d,notpresent,present,index= search(arr_d,n_d,m,ht)
print("\n average no. of collisons for seaching "+str(n_d)+ " elements: "+str(p_d/n))
print("\n no. of succesful searches: "+str(present)+"\n no. of unsuccesful searches: " +str(notpresent))  
