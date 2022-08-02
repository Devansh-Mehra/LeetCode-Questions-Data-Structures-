# LeetCode Questions (Data-Structures)
## Arrays
### Q1.Two Sum

            class Solution {
            public:
                vector<int> twoSum(vector<int>& nums, int target) {
                    int n=nums.size();
                    for(int i=0;i<n;i++)
                    {
                        for(int j=i+1;j<n;j++)
                        {
                            if(target-nums[i]==nums[j]){
                                return {i,j};
                            }
                        }
                    }
                    return {-1,-1};

                }
            };

### Q2. Best Time to buy and sell stock
            
            class Solution {
            public:
                int maxProfit(vector<int>& prices) {
                    int min_prices = prices[0];
                    int profit=0;
                    for(int i=0; i < prices.size(); i++){

                        min_prices = min(min_prices,prices[i]);
                        profit = max(profit, prices[i]-min_prices);

                    }
                    return profit;

                }
            };
           
### Q3. Merge Sorted Arrays
            //when extra space is not allowed
            
            class Solution {
            public:
                void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
                    int i=m-1,j=n-1,k=(m+n)-1;
                    while(i>=0 && j>=0){
                        if(nums1[i]>=nums2[j]){
                            nums1[k--]=nums1[i--];
                        }
                        else{
                            nums1[k--]=nums2[j--];
                        }
                    }
                    while(i>=0){
                        nums1[k--]=nums1[i--];
                    }
                    while(j>=0){
                        nums1[k--]=nums2[j--];
                    }

                }
            };

### Q4. Move Zeroes
            //using 2 pointer approach
            
            class Solution {
            public:
                void moveZeroes(vector<int>& nums) {
                    int j=0;
                    for(int i=0;i<nums.size();i++){
                        if(nums[i]!= 0){
                            nums[j++]=nums[i];
                        }
                    }
                    while(j<nums.size())
                        nums[j++]=0;


                }
            };
            
### Q5. Best Time to buy aand sell stocks II

            class Solution {
            public:
                        int maxProfit(vector<int>& prices) {
                        int net=0;
                        for(int i=1;i<prices.size();i++){
                                    if(prices[i]>prices[i-1]){
                                                net+=(prices[i]-prices[i-1]);
                                    }
                        }
                        return net;
        
        
                        }
            };
