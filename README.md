# -Counts-Subsets-with-Sum-K

TABULATION SOLUTION-->


![image](https://user-images.githubusercontent.com/102652030/174425856-f76b5ea9-4505-4a67-8827-09f49e3ee02b.png)

recurrence for this solution-->

int solution(int i,int target,vector<int> &num,vector<vector<int>> &dp){
    if(target==0){
        return 1;
    }
  if(i==0){
      if(target==num[i]) return 1;
      else return 0;
  } 
    if(dp[i][target]!=-1) return dp[i][target];
    int l=0,r=0;
    l=solution(i-1,target,num,dp);
    if(target>=num[i])
    r=solution(i-1,target-num[i],num,dp);
    
    return dp[i][target]= l+r;
}
