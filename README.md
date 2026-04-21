Intuition :
The brute force way is to check every window of size k and find the maximum → this takes O(n * k) time.

But we can do better using a deque (monotonic queue):

Keep elements in decreasing order
The front always holds the maximum
Remove smaller elements from the back since they’ll never be useful

Approach :
1. Use a queue (q) to store elements in decreasing order.
2. Iterate with two pointers (i, j) forming a sliding window.
3. For each element:
  Remove all smaller elements from the back of the queue.
  Push current element.
4. When window size reaches k:
  The front of the queue is the maximum → add to result.
  If the outgoing element equals the front, remove it.
  Slide the window.

Complexity : 
  Time complexity: O(n)
    Each element is added and removed at most once.
  Space complexity: O(k)
    Queue stores at most k elements.
