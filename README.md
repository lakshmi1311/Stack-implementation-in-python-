# Stack-implementation-in-python-
class stack:
    stack=[None]
    stack_top= -1
    stack_limit=100 
    def __init__(self, size):
        self.stack_limit= size
        self.stack_top= -1
        self.stack=[0]*(size)
    def __setitem__(self,pos, item):
        self.stack[pos]= item
    def push(self, item):
        if ((self.stack_top + 1)  < (self.stack_limit)):
            self.stack_top = self.stack_top + 1
            self.__setitem__(self.stack_top, item)
        else:
            print("Stack is full.")
        return 
    def __getitem__(self, i):
        return self.stack[i]
    def pop(self):
        
        if self.stack_top>=0:
            item= self.__getitem__(self.stack_top)
            self.stack_top= self.stack_top - 1
            return item
        else:
            print("Empty stack")
        return "error"
    
    

s= stack(4)
print( "s.stack_top before push = ", s.stack_top)
print( "s.stack_limit before push = ", s.stack_limit)
s.push(4)
s.push(2)
s.push(5)
s.push(7)
print( "s.stack_top after push of 7 = ", s.stack_top)
s.push(8)
print("First pop =", s.pop())       
print("Second pop = ", s.pop())
print("Third pop =", s.pop())
print("Fourth pop = ", s.pop())
print("Fifth pop = ", s.pop())
print("Sixth pop = ", s.pop())
