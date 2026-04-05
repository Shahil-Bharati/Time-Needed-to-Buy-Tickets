/*         Scroll down to see JAVA code also        */
/*
    Company Tags                : 
    Leetcode Link               : https://leetcode.com/problems/time-needed-to-buy-tickets/
*/

/*********************************************************** C++ **************************************************/
//Approach-1 (Using Queue to simply simulate the operations)
//T.C : O(n*m) -> Loop runs until queue is empty and in worst case all people have maximum m tickets 
//S.C : O(number of tickets)


class Solution {
public:
    int timeRequiredToBuy(vector<int>& tickets, int k) {
        queue<int> q;  // isko isliye bnaye kyuki arr me baar taverse krna padega 
        
        for(int i = 0; i<tickets.size(); i++){
             q.push(i);     // sbke index ko phle push kr diye --
        }
        int time = 0;
        while(tickets[k] != 0){ // yha pr check kr ki ticket kth elemnt Zero kb tk hoga 
          tickets[q.front()]--;   // har elemnt ko -- kro ek se 
          if(tickets[q.front()]) // fir check kro ki ith elemnt Zero or ki bada h zero se
            q.push(q.front());  // zero se bada h to push krdo 
            q.pop();            // start se us elemnt ko pop krdo 
            time++;            // time ko plus plus kro
            
        }
         return time;        
    }

};

