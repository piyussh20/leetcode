# leetcode
to improve coding skills
 
2.two sum

    class Solution {
    public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> result;
        for(int i=0;i<nums.size();i++)
        {
        for(int j=i+1;j<nums.size();j++)
        {
            if(nums[i]+nums[j]==target)
            {
                result.push_back(i);
                result.push_back(j);
                 return result;
            }
        }
        }
        return result;
        
    }
};



4.median of two sorted arrays
        
        class Solution {
        public:
        double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        vector<int> result;
        double median=0;
        int size;

        for(int i=0;i<nums1.size();i++)
        {
            result.push_back(nums1[i]);
        }
        for(int i=0;i<nums2.size();i++)
        {
            result.push_back(nums2[i]);
        }
       size=result.size();
       sort(result.begin(),result.end());
        if(size%2!=0)
        {
        median=result[size/2];
        }
        else 
        {
            median=(result[size/2-1]+result[size/2])/2.0;
        }

        return median;
    }
     };
2200.find all k distant indices in an array
    
    class Solution {
      public:
    vector<int> findKDistantIndices(vector<int>& nums, int key, int k) {
        vector<int> keyIndices;
        vector<int> result;

       
        for (int i = 0; i < nums.size(); ++i) {
            if (nums[i] == key) {
                keyIndices.push_back(i); // 2   5
            }
        }

         
        for (int i = 0; i < nums.size(); i++) { // 0 to 6
            for (int index : keyIndices) {
                if (abs(i - index) <= k) {
                    result.push_back(i);
                    break;  
                }
            }
        }

        return result;
    }
    };
