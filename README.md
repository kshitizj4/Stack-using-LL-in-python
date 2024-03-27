# Stack-using-LL-in-python


from sys import stdin

#Following is the structure of the node class for a Singly Linked List
class Node :

    def __init__(self, data) :
        self.data = data
        self.next = None


class Stack :

    #Define data members and __init__()
    def __init__(self):
        self.__head = None
        self.__size = 0
    '''----------------- Public Functions of Stack -----------------'''



    def getSize(self) :
        #Implement the getSize() function
        return self.__size

    def isEmpty(self) :
        #Implement the isEmpty() function
        return self.__size == 0

    def push(self, item) :
        #Implement the push(element) function
        newNode = Node(data)
        if self.__head is None:
            self.__head = newNode
        else:
            newNode.next = self.__head
            self.__head = newNode
        self.__size +=1

    def pop(self) :
        #Implement the pop() function
        if self.__head is None:
            return -1
        ans = self.__head.data
        self.__head = self.__head.next
        self.__size -=1
        return ans


    def top(self) :
        #Implement the top() function
        if self.__head is None:
            return -1
        return self.__head.data



#main
q = int(stdin.readline().strip())

stack = Stack()

while q > 0 :

    inputs = stdin.readline().strip().split(" ")
    choice = int(inputs[0])

    if choice == 1 :
        data = int(inputs[1])
        stack.push(data)

    elif choice == 2 :
        print(stack.pop())

    elif choice == 3 :
        print(stack.top())

    elif choice == 4 : 
        print(stack.getSize())

    else :
        if stack.isEmpty() :
            print("true")
        else :
            print("false")

    q -= 1
