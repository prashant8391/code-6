# code-6
#Creating node class

class node:

    def __init__(self,data):
        self.data=data
        self.next=None

# Creating linked list class

class linked_list:

    def __init__(self):
        self.head=None


# Creating function for inserting a node

    def insert(self,new_data):
        new_node=node(new_data)
        temp=self.head

        while(temp!=None and temp.next!=None):
            temp=temp.next

        if(temp!=None):
            temp.next=new_node
        else:
            temp=new_node
            self.head=new_node

    
# Creating function for deleting a node when position of a node is given

    def delete_node(self,position):

        if(self.head==None): # Empty linked list
            return

        temp=self.head

# For deleting position 0 node


        if(position==0):
            self.head=temp.next # Sending header to next node
            temp==None
            return

# For removing node after position 0 (any other node)

        for i in range(1,position-1):
            temp=temp.next

            if(temp==None): # If null pointer is reached
                break

# If position is greater than number of nodes

        if(temp==None and temp.next==None):
            return
        

# Deleting temp.next node, so storing its pointer in a variable 'next'

        next=temp.next.next

# Unlinking deleted node from the list
        temp.next=None

        temp.next=next


# Creating a function for printing a linked list


    def print_list(self):
        temp=self.head
        while(temp):
            print(temp.data)
            temp=temp.next


if(__name__=='__main__'):

    llist=linked_list()
    llist.insert(129)
    llist.insert(485)
    llist.insert(288)
    llist.insert(582)
    print("The linked list is given as:")
    llist.print_list()
    llist.delete_node(1)
    print("The linked list after removing the given position node is:")
    llist.print_list()
    


