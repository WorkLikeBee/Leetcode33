class Solution {
    public int search(int[] nums, int target) {
        if(target > nums[nums.length-1] && target < nums[0]){
            return -1;
        }
        int k = kCounter(nums);
        
        if (k==nums.length-1){
            return binarySearch(nums, 0, nums.length-1, target);
        }
        else{
            if (target<=nums[nums.length-1]){
                return binarySearch(nums, k+1, nums.length-1, target);
            }
            else{
                return binarySearch(nums, 0, k, target);
            }
        }   
    }

    // Finding the k value, at which the array was rotated
    public int kCounter(int[]nums){
        int counter = 0;
        int currentIndex = 0;
        int nextIndex = 1;
        if (nums.length == 1){
            return 0;
        }
        else{
            while(nextIndex < nums.length && nums[currentIndex]<nums[nextIndex]){
                counter++;
                currentIndex++;
                nextIndex++;
            }
            return counter;
              
        }
    }

    // Binary search recursive method
    public int binarySearch(int[]nums, int left, int right, int target){
        if(left>right){
            return -1;
        }
        int mid = (left+right)/2;
        if(nums[mid]==target){
            return mid;
        }
        else{
            if (nums[mid] < target){
                return binarySearch(nums, mid+1, right, target);
            }
            else{
                return binarySearch(nums, left, mid-1, target);
            }
        }
    }
}
