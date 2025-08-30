# Lowe-s_India_Interview_Material
Lowe-s India Interview Material

1.Given a string, reverse the order of words.

TYPE 1)
Example 1:

Input: s = "the sky is blue"
Output: "blue is sky the"
Example 2:

Input: s = "  hello world  "
Output: "world hello"
Explanation: Your reversed string should not contain leading or trailing spaces.

Solution):-

class Solution {
    public String reverseWords(String s) {
        s=s.trim();
        String str[]=s.split("\\s+");
        String ans="";

        for(int i=str.length-1;i>=0;i--)
        {
            ans = ans+ " "+str[i];
        }
        return ans.trim();

    }
}

TYPE 2)
Example
Input: "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"

Solution):-

public class Solution {
    
    public String reverseWords(String s) {
        // Write your code here

        s=s.trim();
        String str[]=s.split("\\s+");

        String ans="";
        for(int i=0;i<str.length;i++)
        {
            StringBuilder sb=new StringBuilder(str[i]).reverse();
            ans += sb.toString()+ " ";
        }

        return ans.trim();
    }
}

2.Given a sorted array that has been rotated,find the index of a target element.

TYPE 1)
There is an integer array nums sorted in ascending order (with distinct values).
Example 1:

Input: nums = [4,5,6,7,0,1,2], target = 0
Output: 4
Example 2:

Input: nums = [4,5,6,7,0,1,2], target = 3
Output: -1
Example 3:

Input: nums = [1], target = 0
Output: -1

Solution):-
class Solution {
    public int search(int[] nums, int target) {
        
        int n=nums.length;
        int i=0,j=n-1;
        
        while(i<=j)
        {
            int mid=i+(j-i)/2;
            if(nums[mid] == target)return mid;

            else if(nums[mid]>=nums[i])
            {
                if(target>=nums[i] && target <nums[mid])
                {
                    j=mid-1;
                }
                else{
                    i=mid+1;
                }
            }

            else if(nums[mid]<=nums[j])
            {
                if(target<=nums[j] && target > nums[mid])
                {
                    i=mid+1;
                }
                else{
                    j=mid-1;
                }
            }
        }
        return -1;
    }
}

TYPE 2)
There is an integer array nums sorted in non-decreasing order (not necessarily with distinct values).

Example 1:

Input: nums = [2,5,6,0,0,1,2], target = 0
Output: true
Example 2:

Input: nums = [2,5,6,0,0,1,2], target = 3
Output: false

class Solution {
    public boolean search(int[] nums, int target) {
        int n=nums.length;

        int i=0,j=n-1;

        while(i<=j)
        {
            int mid=i+(j-i)/2;
            if(nums[mid] == target)return true;

            if(nums[mid] == nums[i])
            {
                i++;
                continue;
            }

            else if(nums[mid] >= nums[i])
            {
                // if(nums[i] == target)return true;
                // else 
                if(target >= nums[i] && target < nums[mid])
                {
                    j=mid-1;
                }
                else
                {
                    i=mid+1;
                }
            }
            else if(nums[mid] <= nums[j])
            {
                // if(nums[j] == target)return true;
                // else
                if(target <= nums[j] && target  > nums[mid])
                {
                    i=mid+1;
                }
                else{
                    j=mid-1;
                }
            }
        }
        return false;
    }
}

3.Given an array of distinct integers candidates and a target integer target, return a
  list of all unique combinations of candidates where the chosen numbers sum to target.
  You may return the combinations in any order. 
  The same number may be chosen from candidates an unlimited number of times. 
  Two combinations are unique if the frequency of at least one of the chosen numbers is different.
  You are allowed to use the same number of candidates as many times as needed.
  Example: For nums = [2, 3, 6, 7] and target = 7, the combinations are [7] and [2, 2, 3].

  TYPE 1)Combination Sum1
  Example 1:

Input: candidates = [2,3,6,7], target = 7
Output: [[2,2,3],[7]]
Explanation:
2 and 3 are candidates, and 2 + 2 + 3 = 7. Note that 2 can be used multiple times.
7 is a candidate, and 7 = 7.
These are the only two combinations.
Example 2:

Input: candidates = [2,3,5], target = 8
Output: [[2,2,2,2],[2,3,3],[3,5]]
Example 3:

Input: candidates = [2], target = 1
Output: []

Solution):-
class Solution {
    public List<List<Integer>> combinationSum(int[] candidates, int target) {
        List<List<Integer>> arr=new ArrayList<>();
        makeCombinations(0,candidates,target,arr,new ArrayList<>());
        return arr;
    }

    public void makeCombinations(int ind, int[] candidates, int target, List<List<Integer>> arr, List<Integer> ds)
    {
        if(ind == candidates.length)
        {
            if(target == 0)
            {
                arr.add(new ArrayList<>(ds));
            }
            return;
        }

        if(candidates[ind] <= target)
        {
            ds.add(candidates[ind]);
            makeCombinations(ind,candidates,target-candidates[ind],arr,ds);//picked option
            ds.remove(ds.size()-1);//backtracking
        }

        makeCombinations(ind+1,candidates,target,arr,ds);//not picked option
    }
}

TYPE 2)
Given a collection of candidate numbers (candidates) and a target number (target), find all unique combinations in candidates where the candidate numbers sum to target.

Each number in candidates may only be used once in the combination.

Note: The solution set must not contain duplicate combinations.

 

Example 1:

Input: candidates = [10,1,2,7,6,1,5], target = 8
Output: 
[
[1,1,6],
[1,2,5],
[1,7],
[2,6]
]
Example 2:

Input: candidates = [2,5,2,1,2], target = 5
Output: 
[
[1,2,2],
[5]
]

Solution 1):-
class Solution {
    public List<List<Integer>> combinationSum2(int[] candidates, int target) {

        Arrays.sort(candidates);
        Set<List<Integer>> ans = new HashSet<>();
        List<List<Integer>> arr=new ArrayList<>();
        makeCombinations(0,candidates,target,ans,new ArrayList<>());
        //Convert Set of List into List of List
        arr.addAll(ans);
        return arr;
    }

    public void makeCombinations(int ind,int[] candidates,int target, Set<List<Integer>> ans, List<Integer> ds)
    {
        if(ind == candidates.length)
        {
            if(target == 0)
            {
                ans.add(new ArrayList<>(ds));
            }
            return ;
        }

        if(candidates[ind] <= target)
        {
            ds.add(candidates[ind]);
            makeCombinations(ind+1,candidates,target-candidates[ind],ans,ds);
            ds.remove(ds.size()-1);
        }

        makeCombinations(ind+1,candidates,target,ans,ds);

    }
}

//T.C.:- 2^n*(klogn) by pick and non-pick approach
//Giving TLE:-Time Limit Exceeded

Solution 2):-
class Solution {
    public List<List<Integer>> combinationSum2(int[] candidates, int target) {

        List<List<Integer>> arr=new ArrayList<>();
        Arrays.sort(candidates);
        makeCombinations(0,candidates,target,arr,new ArrayList<>());
        return arr;
    }

    public void makeCombinations(int ind,int[] candidates,int target, List<List<Integer>> ans, List<Integer> ds)
    {
        if(target == 0)
        {
            ans.add(new ArrayList<>(ds));
            return;
        }

        for(int i=ind;i<candidates.length;i++)
        {
            if(i>ind && candidates[i]==candidates[i-1])continue;
            if(candidates[i]>target)break;

            ds.add(candidates[i]);
            makeCombinations(i+1,candidates,target-candidates[i],ans,ds);
            ds.remove(ds.size()-1);
        }
    }
}

//T.C:- 2^n * k
//S.C:-k*x
//Hence ,it's looping from index to n-1 in each and every recursion call.(Sequential Approach)

TYPE 3)
Given an array of distinct integers nums and a target integer target, return the number of possible combinations that add up to target.

The test cases are generated so that the answer can fit in a 32-bit integer.

 

Example 1:

Input: nums = [1,2,3], target = 4
Output: 7
Explanation:
The possible combination ways are:
(1, 1, 1, 1)
(1, 1, 2)
(1, 2, 1)
(1, 3)
(2, 1, 1)
(2, 2)
(3, 1)
Note that different sequences are counted as different combinations.
Example 2:

Input: nums = [9], target = 3
Output: 0
 

Constraints:

1 <= nums.length <= 200
1 <= nums[i] <= 1000
All the elements of nums are unique.
1 <= target <= 1000

Solution:-
class Solution {
    public int combinationSum4(int[] nums, int target) {
        //mamoization
        int dp[]=new int[target+1];
        for(int i=0;i<dp.length;i++)
        {
            dp[i]=-1;
        }
        return solve(nums,target,dp);
    }

    public int solve(int[] nums,int target,int[] dp)
    {
        if(target<0)
        {
            return 0;
        }

        if(target == 0)
        {
            return 1;
        }

        if(dp[target] != -1)
        {
            return dp[target];
        }

        int ans=0;
        for(int i=0;i<nums.length;i++)
        {
            ans += solve(nums,target-nums[i],dp);
        }

        dp[target]=ans;
        return dp[target];
    }
}

4.Given a string s, find the length of the longest substring without repeating characters.

TYPE 1:-
Example 1:

Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
Example 2:

Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.

Solution):-
class Solution {
    public int lengthOfLongestSubstring(String s) {
        int n=s.length();
        int start=0,maxlen=0;

        HashMap<Character,Integer> map=new HashMap<>();
        for(int end=0;end<n;end++)
        {
            char c=s.charAt(end);
            if(map.containsKey(c) && map.get(c)>=start)
            {
                start=map.get(c)+1;
            }
            map.put(c,end);
            maxlen=Math.max(maxlen,end-start+1);
        }

        return maxlen;
    }
}

5.If frequent insertions and deletions occur, which data structure would you choose and why?
   
6.How you connect Kafka to spring boot project
 1. How Microservices Communicate with eachother
 2. How HashMap internally work and how you resolve the collision
 3. Reverse a Stack
 4. Best time to buy a stock
answer:-To connect Kafka to Spring Boot project, add Kafka dependencies in pom.xml and configure Kafka properties in application.properties

Microservices communicate with each other through REST APIs or message brokers like Kafka or RabbitMQ

HashMap internally uses an array of buckets to store key-value pairs. Collision is resolved by chaining or open addressing

To reverse a stack, use an auxiliary stack to pop elements from the original stack and push them into the auxiliary stack

Best time to buy a stock is when the price is low and expected to rise in the future.

7.Combination sum

8.Longest substring with no repeated characters
   
9.Subtract two Linked list

10.Trim Binary Tree

11.
