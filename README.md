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


594.longest harmonium subsequence

            class Solution {
         public:
     
    int findLHS(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        int j = 0, maxLength = 0;

        for (int i = 0; i < nums.size(); ++i) {
            while (nums[i] - nums[j] > 1) {
                j++;
            }
            if (nums[i] - nums[j] == 1) {
                maxLength = max(maxLength, i - j + 1);
            }
        }
        return maxLength;
    }
    };

7.reverse integer
  
  
      class Solution {
     public:
    int reverse(int x) {
        int ans = 0;  
        while (x != 0) {
            int digit = x % 10;  
            
             
            if ((ans > INT_MAX / 10) || (ans < INT_MIN / 10)) {
                return 0;  
            }
            
            ans = ans * 10 + digit;  
            x = x / 10; 
        }
        return ans;  
    }
     };

        return result;
    }
    };
9.palindrome number
     
    class Solution {
    public:
    bool isPalindrome(int x) {
        int temp=0;
        bool answer;
        int ans = 0;
        temp=x;  
        while (x != 0) {
            int digit = x % 10;  
            
             
            if ((ans > INT_MAX / 10) || (ans < INT_MIN / 10)) {
                return 0;  
            }
            
            ans = ans * 10 + digit;  
            x = x / 10; 
        }
        
         if(temp==ans)
         {
            answer=true;
         }  
         
         if(temp!=ans)
         {
            answer=false;
         }
          if(temp<0)
         {
            answer=false;
         }


 
         return answer;
    }
    }; 
   
3300.find the original typed string

     class Solution {
     public:
    int possibleStringCount(string word) {
        int size = word.length();
        int count = 1;

        for (int i =1; i < size; i++) {
            
                if (word[i] == word[i-1]) {
                    count++;
                }
            
        }

12.integer to roman
    
    class Solution {
    public:
    string intToRoman(int num) {
        string thousands[] = {"", "M", "MM", "MMM"};
        string hundreds[]  = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"};
        string tens[]      = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"};
        string ones[]      = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"};

        return thousands[num / 1000] +
               hundreds[(num % 1000) / 100] +
               tens[(num % 100) / 10] +
               ones[num % 10];
    }
    };

 
         return count;
     }
     };
