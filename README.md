# Almabase_Software_Engineer_Intern
## Almabase Engineer Task Round

This project uses GITHUB API to retrieve the results of N most popular repositories out of K Total repositories and their M top contributors.

Various optimazation method used in the project are:
- One of the major optimization method used to find N most popular repository out of many repository is the use of MIN-HEAP, which decreased the output time very much. For example 

  - First method is to get N most popular is to store the result in List and then sort the result in non-increasing order based on the number of forks and use list[0] to list[N-1] items followed by top M contributors of each repository respectively.
  Time Complexity of this method is **O(KlogK) + O(NM)** and **Space Complexity is O(k)**
  
  - Second and the most effective method used in this project is to use MIN-HEAP:
    - Build a MIN_HEAP list of the first N elements (list[0] to list[N-1]) of the given array. For each element, after the Nth element (list[N] to list[K-1]), compare it with root of MIN_HEAP
    - If the element is greater than the root then make it root and call heapify for list, Else ignore it.
    - Finally, list has N largest elements and root of the MIN-HEAP is the Nth largest element.
  Time Complexity of this method is **O(N + (K-N)LogN) + O(NM)** and **Space Complexity is O(N)** </br></br>
  **As we can see we are only dealing with largest N elements not with Total elements which will eventually decrease space and time complexity as well.**
  
  
  K = Total repository, N = top repository with maximum fork count, m = top contributors of respective repository.
 - Second important method used to retrieve list of all repository of a given organization using GITHUB API is that using recursive function to iterate through all the pages because by default GitHub Search API provides items in sets of 100 per page and makes them in pagination. To iterate through all these pages we used recursion function to traverse through all pagination.
