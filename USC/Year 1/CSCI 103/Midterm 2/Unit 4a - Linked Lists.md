- Stores values in separate chunks of memory
- To know where the next one is, each one stores a pointer to the next
- All we do is track the first item (head pointer)
- Last item holds the NULL pointer


#### Arrays vs Linked List
Pro: Ability to resize
Con: Sacrifice speed of access when attempting to get the element at an arbitrary location

### Building a Linked List
```c++
struct Item {
	int val;
	Item* next;
};
class List {
	public:
		List();
		~List();
		void push_back(int v); ...
	private:
		Item* head;
};

```

```c++
#include<iostream>
using namespace std;
List::List()
{
head = NULL; //initializing
}

void List::push_back(int v){
	if(head == NULL){ // list is empty
		head = new Item; //declare
		head->val = v; //initializing
		head->next = NULL; //making it null because it is an empty list
	}

	// what to do if the list is not empty
	else { 
	// Iterate to last element
			Item* temp = head;
		while(temp->next != NULL) {
			temp = temp->next // take a step
		}
		Item* newp = new Item;
		newp->val = v; newp->next = NULL;
		temp->next = newp;
	}
}

int main() {
List mylist;
mylist.push_back(3);
mylist.push_back(9);
mylist.push_back(2);
}


```

**Don't lose the head**
If we change head we have no way to back to the old first item




