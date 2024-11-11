# Assignment-3
# Algorithm Efficiency and Scalability
This project implements and analyzes the efficiency and scalability of two algorithms:
- Randomized Quicksort
- Hashing with Chaining


Randomized Quicksort: A sorting algorithm that picks a pivot randomly to ensure better performance in the average case.
Hashing with Chaining: A classic method for resolving hash table collisions using linked lists.
Through this project, I’ve compared their performance both theoretically and experimentally. Let me walk you through the steps to run the code and summarize the key takeaways!


🚀 How to Get Started
First things first! Before you can run the code, you’ll need to make sure everything is set up correctly. Here’s what you need to do:


1. Install Python
Make sure you’ve got Python 3.x installed on your machine. You can grab it from here.


2. Install Dependencies (If Any)
For the most part, the code runs without needing any special libraries. However, for running the performance tests or if you want to visualize the results, you'll need a couple of additional Python packages. You can install them using pip:


bash
Copy code
pip install matplotlib numpy
🧑‍💻 How to Run the Code
Now let’s get into the fun part—running the code! Here's how you can test everything out:


Part 1: Randomized Quicksort
Randomized Quicksort Implementation:


The algorithm is implemented in the randomized_quicksort.py file. You can test it by calling the function like this:


python
Copy code
from randomized_quicksort import randomized_quick_sort


# Let's test the algorithm with an example array
arr = [12, 4, 7, 9, 1, 14]
print("Before Sorting:", arr)
randomized_quick_sort(arr)
print("After Sorting:", arr)
You’ll see that the array gets sorted in place using Randomized Quicksort.


Empirical Comparison:


Want to see how Randomized Quicksort stacks up against Deterministic Quicksort? I’ve created a script in compare_algorithms.py that compares their performance across different types of arrays (random, sorted, reverse-sorted, etc.).


Just run:


python
Copy code
from compare_algorithms import run_comparison


run_comparison()  # This will run comparisons and print the results
You’ll get a breakdown of how long each algorithm takes on different inputs. This is useful to see how the randomness in the pivot selection affects performance.


Part 2: Hashing with Chaining
The Hash Table:


The hash_table.py file contains the hash table implementation. To try it out:


python
Copy code
from hash_table import HashTable


# Create a hash table
ht = HashTable()


# Insert some key-value pairs
ht.insert(10, 'Value 1')
ht.insert(20, 'Value 2')


# Search for a key
print(ht.search(10))  # Output: 'Value 1'


# Delete a key-value pair
ht.delete(20)
print(ht.search(20))  # Output: None (because it's deleted)
You’ll see how the hash table works for inserting, searching, and deleting key-value pairs. The chaining method handles collisions using linked lists.


📊 Summary of Findings
Randomized Quicksort:
Theoretical Analysis: The average-case time complexity of Randomized Quicksort is O(n log n). By choosing a random pivot, we avoid the worst-case performance that arises in deterministic Quicksort when the input is sorted or reverse-sorted.


Empirical Results:


On random arrays, Randomized Quicksort consistently performs better than Deterministic Quicksort.
For sorted arrays and reverse-sorted arrays, Deterministic Quicksort can degrade to O(n^2) time complexity, which is pretty slow. But Randomized Quicksort still performs in O(n log n) time, even for these tricky inputs.
Arrays with repeated elements don’t affect Randomized Quicksort as much, while Deterministic Quicksort can still face issues when elements are duplicated.
Hashing with Chaining:
Theoretical Performance: For a well-distributed hash function, both search, insert, and delete operations should be O(1) on average. However, performance degrades as the table gets full and the load factor increases. This leads to longer chains, and thus, longer search times.


Empirical Results:


As the table fills up, collisions increase, and the operations start to take longer. If you want to keep performance smooth, you can resize the table (rehash) when the load factor gets too high.
By dynamically resizing the table (doubling the size when the load factor exceeds a certain threshold), the performance remains efficient even as more elements are inserted.
📝 Conclusion
Randomized Quicksort is generally more efficient than Deterministic Quicksort, especially in the average case. Its random pivot selection gives it an edge in real-world scenarios where inputs can be unpredictable.


Hashing with Chaining is efficient when the load factor is kept low, but it suffers as more elements are added. Resizing the hash table (rehashing) helps maintain its performance.

