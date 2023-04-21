# maximum-sub-array

#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int maxSubarraySum(const vector<int>& nums) {
    int maxSum = INT_MIN, currSum = 0;
    for (int num : nums) {
        currSum += num;
        maxSum = max(maxSum, currSum);
        currSum = max(currSum, 0);
    }
    return maxSum;
}

int main() {
    vector<int> nums = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
    int maxSum = maxSubarraySum(nums);
    cout << "The maximum subarray sum is: " << maxSum << endl;
    return 0;
}
