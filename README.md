# Lowe-s_India_Interview_Material
Lowe-s India Interview Material

1.Given a string, reverse the order of words.
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

2.Given a sorted array that has been rotated,find the index of a target element.

3.Given an array of distinct integers candidates and a target integer target, return a
  list of all unique combinations of candidates where the chosen numbers sum to target.
  You may return the combinations in any order. 
  The same number may be chosen from candidates an unlimited number of times. 
  Two combinations are unique if the frequency of at least one of the chosen numbers is different.
  You are allowed to use the same number of candidates as many times as needed.
  Example: For nums = [2, 3, 6, 7] and target = 7, the combinations are [7] and [2, 2, 3].
  
4.Given a string s, find the length of the longest substring without repeating characters.

5. If frequent insertions and deletions occur, which data structure would you choose and why?
   
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
