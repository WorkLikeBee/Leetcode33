# Leetcode33
Search in rotated array

The solution is based on the idea of binary search algorithm. 
* Since the array is rotated, we can dived the array into two regions, and each othem will contains an order of increasing elements. For ex: [4,5,6,1,2,3] can be divided into [4,5,6] and [1,2,3].
  => So the idea is we can divide the array into two region (if needed), then we will know the target will be placed in what region since every elements are unique.
  For ex: if target is 2 then we will know it is laid on the 2nd region.
      * Actually, we can check whether the target is in  region 1 or region 2 generally. If we compare the target with the last element of region 2 and first element of region, we may know the target is in which boundary.
            => Take the example above, since target = 2 is smaller than 3 then it's obviously in 2nd region. Then we just need to do the binary search in then 2nd region. Otherwise, we'll do binary search in the 1st region.

But how do we divide the regions? Do we just divide them randomly? 
Take [4,5,6,1,2,3] for example. If I want to count how many items I have in region 1, I start at 4 and count. So I'll 4->5->6, which is followed the increasing order. Then, after 6 is a break point 4->5->6->1
    => So in region 1 there should be 3 items [4,5,6]. 
    => Based on that idea, I create a method called kCounter to find how many items I have in region 1
            + I used while loop to traverse through the area and used two pointers (current and next). Also, I initialized a counter equals to 0
            + As the current and next index updating, if the current element < the next element, then increase the counter by 1.
            + After the while loop is completed, I return the value of the counter.
    Caution: for the example above, the kCounter method will return 2, but there are 3 elements in region 1, so the method only returns the # of element - 1.
              Since I want to access the last index of the region 1, I create the method so that kCounter will give the value of the last index in the region 1.

