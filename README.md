# uniquepermutations
class Solution {
public:
    void solve(vector<vector<int>>&res,int j,vector<int>&nums){
        if(j==nums.size()){
            res.push_back(nums);
            return;
        }
        for(int i=j;i<nums.size();i++){
            if(i==j||nums[i]!=nums[j]){
            swap(nums[i],nums[j]);
            solve(res,j+1,nums);
            swap(nums[i],nums[j]);}
        }
    }
    vector<vector<int>> permuteUnique(vector<int>& nums) {
        vector<vector<int>>res;
        sort(nums.begin(),nums.end());
        solve(res,0,nums);
        return res;
    }
};
