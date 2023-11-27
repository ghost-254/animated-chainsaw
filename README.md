**Inversion Count by Divide-and-Conquer: A Merge-Sort Approach**
*****************************************************************************************************************************
**Abstract**
******************************************
This project explores the efficiency of inversion counting and array sorting algorithms, with a focus on the Merge-Sort with inversions approach compared to the brute-force method. The code execution is conducted on Google Colab, a cloud-based platform, allowing for seamless integration with Python libraries and convenient collaboration. The study uncovers a sorting discrepancy in the brute-force implementation, where the original and brute-force sorted array graphs unexpectedly align. Although, the Merge-Sort algorithm emerges as less efficient in terms of time due to limited storage and RAM allocation at Google Colab, spacing, completing in 25 seconds compared to the brute-force's 7 seconds, the fact still remains that it showed more efficiency in terms of the large datasets that were generated at random. These findings highlight the importance of algorithmic accuracy and efficiency and prompt further investigation into the sorting logic of the brute-force method. Recommendations include optimizing the brute-force approach and addressing potential memory limitations for larger datasets within the Google Colab environment.

Key Words: Inversion Counting, Array Sorting Algorithms, Merge-Sort with Inversions, Brute-Force Method, Google Colab, Code Execution, Algorithmic Efficiency
**********************************************************************************************************************************************
**Inversion Count by Divide-and-Conquer: A Merge-Sort Approach**
The idea of inversion count has significant importance in the field of algorithmic analysis as it quantifies the extent to which an array diverges from a sorted state. An inversion is said to occur in an array when two items inside the array are positioned in reverse order relative to their respective indices. The importance of the inversion count is seen in its wide-ranging applications within several domains, including sorting algorithms, data analysis, and optimization challenges. This study specifically examines the task of counting inversions inside an array, using the divide-and-conquer technique via the merge-sort method and a close comparison to brute-force method. In this particular context, the merge-sort method, renowned for its effectiveness in sorting extensive datasets, has been modified to not only provide a sorted array but also quantify the quantity of inversions that exist therein.
**********************************************
*Project Purpose*
The objective of this research is to provide a comprehensive analysis of the inversion count issue, elucidating the use of the merge-sort method in tackling this particular obstacle. The study aims to provide insights into efficient inversion count procedures by presenting a detailed algorithmic breakdown, accompanied by a theoretical and practical investigation of its complexity. The primary objective is to conduct a comparative analysis of the efficiency of the merge-sort algorithm in comparison to a brute-force alternative. This study aims to derive significant insights on the relative benefits and limitations of these two approaches. This paper seeks to augment comprehension, enable comparisons, and provide important perspectives on the wider domain of algorithmic problem-solving.
 ***************************************************************************************************************************************
**Algorithm Design**
*Merge-Sort with Inversions*
The Merge-Sort algorithm is a well-known sorting algorithm that adheres to the divide-and-conquer paradigm. The process is iteratively partitioning an array into progressively smaller subarrays until each subarray consists of a single element, which is intrinsically arranged in sorted order. The process involves merging the sorted subarrays to get a completely sorted array (GeeksforGeeks, 2023a). The merging phase is a crucial component of the process, since it involves the combination of two sorted subarrays to generate a bigger sorted array. The algorithm's temporal complexity may be expressed as O(n log n), with n being the length of the input array. The space complexity of the algorithm is determined to be O(n) as a result of the need for extra space to facilitate the merging of the subarrays (GeeksforGeeks, 2023a).
***********************************************************
Subsequently, in order to include the counting of inversions into the Merge-Sort algorithm, we may use the inherent capability of the merging phase to efficiently count inversions. An inversion refers to a pair of indices (i, j) in which i is less than j and the element at index i in the array is greater than the one at index j (GeeksforGeeks, 2023a). During the merging process, in the event that an element within the left subarray is found to be bigger than an element within the right subarray, it results in the creation of inversions with all the other items present inside the left subarray. In this regard, via the process of monitoring these inversions throughout the merging operation, it becomes possible to compute the overall count of inversions for the whole array.
***************************************************************
*Brute-Force Approach*
The brute-force approach to count inversions involves a nested loop that iterates through each pair of elements in the array and checks if they form an inversion. Even though it is straightforward, this approach has a time complexity of O(n^2), where n is the length of the array, making it less efficient for large datasets compared to the divide-and-conquer approach of Merge-Sort (StudySmarter UK, 2023). It is primarily used for comparison and verification of the results obtained through more efficient algorithms like Merge-Sort with inversion counting.
*Pseudocode*
*******************************
Input: an unsorted array, arr
Output: a sorted array, sorted_arr, and the inversion count, inversion_count
Procedure:
1. If the length of arr is less than or equal to 1:
    1.1 Return arr and set inversion_count to 0
2. Calculate the midpoint (mid) of arr
3. Recursively apply MergeSort to the left half of arr, obtaining left and inv_count_left
4. Recursively apply MergeSort to the right half of arr, obtaining right and inv_count_right
5. Merge the sorted left and right arrays, and count inversions:
    5.1 Call MergeWithInversions(left, right) and assign the result to merged and inv_count_merge
6. Calculate the total inversion count:
    6.1 Set inversion_count_total to the sum of inv_count_left, inv_count_right, and inv_count_merge
7. Return the merged array (sorted_arr) and the total inversion count (inversion_count_total)
Procedure MergeWithInversions(left, right):
1. Initialize an empty array, merged
2. Initialize variables i, j, and inv_count to 0
3. While i is less than the length of left and j is less than the length of right:
    3.1 If left[i] is less than or equal to right[j]:
        3.1.1 Append left[i] to merged and increment i
    3.2 Else:
        3.2.1 Append right[j] to merged, and increment inv_count by the number of remaining elements in left (length(left) - i)
        3.2.2 Increment j
4. Append any remaining elements from left and right to merged
5. Return merged array and inv_count
 ********************************************************************************************
**Complexity Analysis**
*******************************************************************************************
**Theoretical Time Complexity Analysis**
*Merge-Sort*
According to a study conducted by StudySmarter UK in 2023, the Merge-Sort method exhibits a time complexity of O(n log n), where 'n' represents the total number of items present in the array. This time complexity is attributed to the recursive nature of the process. During each recursive invocation, the array undergoes a process of being partitioned into two equal halves until each subarray contains just a single element. Subsequently, the merging operation is performed. The merge operation exhibits a temporal complexity that is directly proportional to the size of the merged subarrays.
***********************************
*Merge-Sort with Inversions*
The adaptation to count inversions does not alter the fundamental structure of Merge-Sort; it simply introduces additional operations during the merging step to count inversions. Therefore, the time complexity of Merge-Sort with inversions remains O(n log n) (StudySmarter UK, 2023). The extra operations during merging are performed in linear time and do not change the overall logarithmic time complexity of the sorting process.
*Theoretical Space Complexity Analysis*
The space complexity of Merge-Sort with inversions is O(n). This complexity arises from the need to create temporary arrays during the merging process. In each recursive call, new arrays are created for the left and right halves of the input array. Additionally, the merging process involves creating a temporary array to store the merged result (StudySmarter UK, 2023). The space complexity is dominated by the recursive calls and the temporary arrays created during the sorting process. Since the maximum depth of the recursion tree is log(n), where 'n' is the number of elements in the array, the space complexity is O(log n) due to the function call stack (StudySmarter UK, 2023). However, the temporary arrays created during the merging steps contribute an additional O(n) space complexity. Therefore, the overall space complexity is O(n + log n), but in big O notation, we generally drop the lower-order terms, leading to a final space complexity of O(n).
*Comparison with Brute-Force*
As mentioned above, Merge-Sort with inversions leverages a divide-and-conquer strategy. The time complexity is dominated by the merging process, which takes linear time during each recursive call, which results in a time complexity of O(n log n) (StudySmarter UK, 2023). On the other hand, the brute-force approach involves checking every pair of elements in the array to identify inversions. This instance leads to a nested loop structure, resulting in a time complexity of O(n^2), where 'n' is the number of elements (GeeksforGeeks, 2023b).
**Advantages and Disadvantages**
*Merge-Sort with Inversions*
*Advantages:*
1.	In terms of efficiency, Merge-Sort with inversions offers superior time complexity (O(n log n)) compared to the brute-force approach (O(n^2)), especially for larger datasets (GeeksforGeeks, 2023b).
2.	In terms of adaptability, the algorithm can be easily adapted for other applications requiring inversion counting without a complete rewrite.
Disadvantages:
1.	Merge-Sort with inversions has a higher space complexity (O(n)) due to the creation of temporary arrays during the merging process, which could be a concern for large datasets in memory-constrained environments (GeeksforGeeks, 2023b).
**Brute-Force Approach**
*Advantages:*
1.	The brute-force approach is straightforward to implement and understand since it involves a simple nested loop structure for comparing all pairs of elements (StudySmarter UK, 2023).
2.	In some scenarios with small datasets or unique requirements, the simplicity of the brute-force approach may be advantageous (StudySmarter UK, 2023).
*Disadvantages:*
1.	In terms of efficiency issues, the time complexity of O(n^2) makes the brute-force approach inefficient for large datasets since it becomes impractical as the size of the dataset increases.
2.	The brute-force approach is not well-suited for scenarios where efficiency is crucial, such as dealing with very large datasets (StudySmarter UK, 2023).
Ultimately, Merge-Sort with inversions is theoretically more efficient than the brute-force approach in terms of time complexity, especially for larger datasets. However, it is essential to understand that the choice between the two approaches depends on the specific requirements of the problem, the size of the dataset, and the available computational resources. Merge-Sort with inversions is well-suited for general-purpose inversion counting in a variety of scenarios, offering a good balance of efficiency and adaptability. On the other hand, the brute-force approach may be more suitable for small datasets or situations where simplicity is prioritized over efficiency. However, it becomes impractical for larger datasets due to its quadratic time complexity. Thus, it is common sense to go with the Merge-Sort approach which covers all these inefficiency issues since it is easier to account for issues related to space capacity than having to deal with issues related to inefficiencies and applicability.
************************************************************
**Results and Analysis**
The author utilized Google Colab, an online platform which provides free Python Notebook to run the Python Script as it is freely available for these development purposes. In the experimental results, the brute-force approach exhibited a runtime of 7 seconds for the first test, significantly lesser than the Merge-Sort with inversions, which ran in 25 seconds. However, an interesting observation arose as the graphs for the brute-force approach displayed no discernible sorting effect; the bars in the graph for the brute-force sorted array were identical to the bars in the original array graph. This discrepancy suggests a potential sorting issue within the brute-force implementation. On the contrary, the Merge-Sort with inversions not only demonstrated efficiency in terms of runtime but also accurately sorted the array. The original array graph displayed random bar lengths, while the sorted array graph exhibited a clear and expected pattern with bars sorted by length. These findings underline the importance of algorithmic accuracy and efficiency, prompting further investigation into the sorting logic of the brute-force approach. Additionally, the efficiency gains of Merge-Sort with inversions emphasize its suitability for scenarios where sorting large datasets is a crucial consideration.
 **************************************************************************************
Figure 1: Brute-Force Algorithm: Original Array vs. Brute-Force Sorted Array Graph
 
Figure 2: Merge-Sort Algorithm: Original Array Graph vs. Sorted Array Graph

******************************************************************************
**Conclusion**
In conclusion, the project highlights the effectiveness of the Merge-Sort with inversions algorithm in efficiently counting inversions and sorting arrays compared to the brute-force approach. The substantial runtime difference, with Merge-Sort completing in 25 seconds against the brute-force's 7 seconds, underscores the algorithmic space efficiency of the latter. However, the unexpected similarity between the original and brute-force sorted array graphs raises concerns about the accuracy of the brute-force implementation. Further investigation into the sorting logic is warranted. Possible improvements include optimizing the brute-force method and exploring more advanced inversion counting techniques. Additionally, the current project implementation may face challenges with memory usage for larger datasets, suggesting potential enhancements in that aspect.
 ************************************************************************************************************
**References**
GeeksforGeeks. (2023a). Inversion count in array using merge sort. GeeksforGeeks. https://www.geeksforgeeks.org/inversion-count-in-array-using-merge-sort/ 
GeeksforGeeks. (2023b, May 31). Time and space complexity analysis of merge sort. GeeksforGeeks. https://www.geeksforgeeks.org/time-and-space-complexity-analysis-of-merge-sort/ 
StudySmarter UK. (2023). Algorithms: Definition, examples & data structures. StudySmarter UK. https://www.studysmarter.co.uk/explanations/computer-science/algorithms-in-computer-science/
