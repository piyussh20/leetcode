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
20.valid parentheses

     class Solution {
    public:
    bool isValid(string s) {
        stack<char> res;
        
        for (int i = 0; i < s.length(); i++) {
            if (s[i] == '(' || s[i] == '[' || s[i] == '{') {
                res.push(s[i]);
            } else {
                if (res.empty()) return false; // no opening to match
                char top = res.top();
                if ((s[i] == ')' && top != '(') ||
                    (s[i] == ']' && top != '[') ||
                    (s[i] == '}' && top != '{')) {
                    return false;
                }
                res.pop(); // matched successfully
            }
        }
        
        return res.empty(); // must be empty for full match
    }
    };

26.remove duplicates from array
    
     class Solution {
    public:
    int removeDuplicates(vector<int>& nums) {
        if (nums.size() == 0) return 0;

        int j = 1;

        for (int i = 1; i < nums.size(); i++) {
            if (nums[i] != nums[i - 1]) {
                nums[j] = nums[i];
                j++;
            }
        }

        return j;
    }
    };

 
         return count;
     }
     };

     
27.remove elements
   
     class Solution {
      public:
    int removeElement(vector<int>& nums, int val) {
        int res=0;
        if (nums.size() == 0) return 0;
        for (int i = 0; i < nums.size(); i++) {
            if (nums[i] == val) {
                continue;
            }
            if(nums[i]!=val)
            {
                nums[res] = nums[i];
                 res++;
            }
        }
        return res;
    }
    };

  
 29.DIVIDE TWO INTEGERS
   
     class Solution { 
    public:
    int divide(int dividend, int divisor) {
     
    if (dividend == INT_MIN && divisor == -1) { /*int x = -2147483648;
    int result = x / -1;   

     but here result would be 2147483648 and the value of INT_MAX is 2147483647 so there is diffrence of 1 so THE 
     CLOSEST NUMBER IS TAKEN AS ANSWER SO HERE IT IS INT_MAX OTHERWISE IT WOULD CAUSE OUT OF BOND ACCESS ERROR
     */
            return INT_MAX;   
        }

        return dividend / divisor;
    }
    };
35.search insert position
     
     class Solution {
    public:
    int searchInsert(vector<int>& nums, int target) {
         int pos;
         
        if(nums[0]>target)
        {
            pos=0;
        }
        for(int i=0;i<nums.size();i++)
        {
        if(nums[i]==target)
        {
            pos=i;
        }
        if(target>nums[nums.size()-1])
        {
            pos=nums.size();
        }
        }
        for(int i=1;i<nums.size();i++)
        {
         if(target>nums[i-1] && target<nums[i])
        {
            pos=ceil((i+i+1)/2);
        }
 33.search in rotated sorted array
       
        class Solution {
        public:
    int search(vector<int>& nums, int target) {
        int pos=-1;
        for(int i=0;i<nums.size();i++)
        {
            if(nums[i]==target)
            {
                pos=i;
            }
        }
         return pos;
    }
  
    };

34.find first and last position of element in a sorted array
       
       class Solution {
     public:
    vector<int> searchRange(vector<int>& nums, int target) {
         int pos=-1,pos2=-1,temp=0;
        for(int i=0;i<nums.size();i++)
        {
            for(int j=nums.size()-1;j>=0;j--)
            {
            if(nums[i]==target)
            {
                pos=i;
            }
             if(nums[j]==target)
            {
                pos2=j;
            }
            }
            
        }
        if(pos>pos2)
        {
        temp=pos;
        pos=pos2;
        pos2=temp;
        }
         return {pos,pos2};
    }
     };
        }



50.pow (x,n)

     class Solution {
    public:
    double myPow(double x, int n) {
      double ans=pow(x,n);
        return ans;
    }  
    };
41.first missing positive
    
    class Solution {
    public:
    int firstMissingPositive(vector<int>& nums) {
        sort(nums.begin(), nums.end());

        int n = 1;
        for (int num : nums) {
            if (num == n) 
            {
                n++;
            }
        }

        return n;
    }
    };
58.length of last word
    
     class Solution {
     public:
    int lengthOfLastWord(string s) {
        int count = 0, pos = -1;
        for (int i = s.length() - 1; i >= 0; i--) {

            if (s[i] != ' ') {
                pos = i;
                break;
            }
        }
        if (pos == -1)
            return 0;
        for (int i = pos; i >= 0; i--) {
            
            if (s[i] == ' ') {
                break;
            }
             count++;
        }
        return count;
        }
        };
  69.sqrt(x)
    
    class Solution {
    public:
    int mySqrt(int x) {
          
    int ans= sqrt(x);
    return ans;
    }  
    };
