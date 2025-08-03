ARRAYS 
Subset:
class Solution:
    def generate(self,ind,curr_subset,ans,nums):
        if(ind==len(nums)):
            ans.append(curr_subset.copy())
            return 
        curr_subset.append(nums[ind])
        self.generate(ind+1,curr_subset,ans,nums)
        curr_subset.pop()
        self.generate(ind+1,curr_subset,ans,nums)
    def subsets(self, nums: List[int]) -> List[List[int]]:
        ind = 0
        curr_subset = []
        ans = []
        self.generate(ind,curr_subset,ans,nums)
        return ans
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
combination sum
class Solution:
    def generate(self,ind,curr_subset,ans,candidates,target):
        if(target==0):
            ans.append(curr_subset.copy())
            return
        if(target<0):
            return 
        if(ind==len(candidates)):
            return
        curr_subset.append(candidates[ind])
        self.generate(ind,curr_subset,ans,candidates,target-candidates[ind])
        curr_subset.pop()
        self.generate(ind+1,curr_subset,ans,candidates,target)
    def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:
        ind = 0
        curr_subset = []
        ans=[]
        self.generate(ind,curr_subset,ans,candidates,target)
        return ans
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        n=len(nums)
        cs=0
        ms=float("-inf")
        for i in  nums:
            cs+=i
            ms=max(ms,cs)
            if(cs<0):
                cs=0
        return ms
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

