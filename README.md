# balancedParentesis

class cl_stack():
    def __init__(self):
        self.st=[]
    def push(self,i):
        self.st.append(i)
    def poop(self):
        if self.is_empty():
            return False
        else:
            return self.st.pop()
    def clear(self):
        for i in self.st:
            self.st.remove(i) 
    def is_empty(self):
        if len(self.st)==0:
            return True
        else:
            return False  
    def pri(self):
        for i in self.st:
            print(i)                  
 
n=int(input())
array=input().split()
array=list(map(int,array))
maxx=0
length=0
stack=cl_stack()
for i in array:
    if i>0:
        stack.push(i)
        state='push'
    else:
        if state=='push' and stack.is_empty()==True:
            length=0
        elif state=='pop' or stack.is_empty()==False:
            length=length    
        state='pop'
        a=stack.poop()
        if a==False:
            continue
        elif a==abs(i):
            length=length+2
            if length>maxx:
                maxx=length
        else:
            
            stack.clear()
            state='push'
           
print(maxx)
