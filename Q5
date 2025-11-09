class HashTable:
    def __init__(self):  
        self.size = 10
        self.table = [[] for _ in range(self.size)]

    def hash_function(self, key):
        return key % self.size

    def insert(self, key, value):
        index = self.hash_function(key)
        chain = self.table[index]

        for i, (k, v) in enumerate(chain):
            if k == key:
                chain[i] = (key, value)
                print(f"Updated key {key} with new value '{value}' at index {index}")
                return

        chain.append((key, value))
        print(f"Inserted key {key} with value '{value}' at index {index}")

    def search(self, key):
        index = self.hash_function(key)
        chain = self.table[index]

        for k, v in chain:
            if k == key:
                print(f"Key {key} found at index {index} with value '{v}'")
                return v

        print(f"Key {key} not found in hash table")
        return None

    def delete(self, key):
        index = self.hash_function(key)
        chain = self.table[index]

        for i, (k, v) in enumerate(chain):
            if k == key:
                del chain[i]
                print(f"Deleted key {key} from index {index}")
                return

        print(f"Key {key} not found. Nothing to delete.")



hash_table = HashTable()
hash_table.insert(10, "Apple")
hash_table.insert(20, "Banana")
hash_table.insert(25, "Cherry")
hash_table.insert(15, "Mango")
hash_table.insert(5, "Orange")

hash_table.search(10)
hash_table.search(99)

hash_table.delete(20)
hash_table.delete(99)


class CallCenterQueue:
    def __init__(self):  
        self.queue = []

    def addCall(self, customerID, callTime):
        call = {"customerID": customerID, "callTime": callTime}
        self.queue.append(call)
        print(f"Call from Customer {customerID} added at {callTime} minutes.")

    def answerCall(self):
        if not self.isEmpty():
            call = self.queue.pop(0)
            print(f"Answered call from Customer {call['customerID']} (Call time: {call['callTime']} mins).")
        else:
            print("No calls in the queue to answer!")

    def viewQueue(self):
        if not self.isEmpty():
            print("Current Call Queue:")
            for i, call in enumerate(self.queue, start=1):
                print(f"Call {i}: Customer ID: {call['customerID']}, Call Time: {call['callTime']} minutes")
        else:
            print("The call queue is empty.")

    def isEmpty(self):
        return len(self.queue) == 0


call_center = CallCenterQueue()

while True:
    print("\n--- Call Center Menu ---")
    print("1. Add Call")
    print("2. Answer Call")
    print("3. View Queue")
    print("4. Check if Queue is Empty")
    print("5. Exit")

    choice = input("Enter your choice (1-5): ")

    if choice == "1":
        customerID = input("Enter Customer ID: ")
        callTime = input("Enter Call Time (in minutes): ")
        call_center.addCall(customerID, callTime)

    elif choice == "2":
        call_center.answerCall()

    elif choice == "3":
        call_center.viewQueue()

    elif choice == "4":
        if call_center.isEmpty():
            print("The call queue is empty.")
        else:
            print("The call queue is not empty.")

    elif choice == "5":
        print("Exiting Call Center Simulation. Goodbye!")
        break

    else:
        print("Invalid choice. Please enter a number between 1 and 5.")
