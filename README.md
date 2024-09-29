# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.

Add your answers to this markdown file.

## Answer

Under the assumption that this algorithm sorts in $O(n)$ time, I can think of a good way to test this. If you have a dataset $n$ that runs at a time of $x$, then the dataset of size $2n$ should run at a time of $2x$. I would create multiple lists of sizes from 100 to 1,000,000. I would log the run time for each input size multiple times, and find an average run time for each input size. I would then run a different comparison based sorting algorithm, such as mergesort, and calculate an average run time for each input size as well. X should scale linearlly, as the time complexity suggests. If the run time scales logarithmically, exponentially, or anything other than linearly, the algorithm does not truly sort in $O(n)$ time. It will be easy to see when compared to another sorting algorithm on a graph.

I believe that this just cannot be correct. The best case for a sorting algorithm is insertion sort, it runs at $O(n)$ *if* all the elements are already sorted. Without having a specialized case, or some kind of presorted dataset, I believe that it is not possible for a general sorting algorithm like this to have a time complexity of $O(n)$. The low bound for comparisons in any comparison based sorting algorithm is $O(nlogn).

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

Source: https://zoo.cs.yale.edu/classes/cs201/topics/topic-sorting-lb.pdf
