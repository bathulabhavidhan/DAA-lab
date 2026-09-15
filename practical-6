#include <iostream>
#include <vector>
#include <climits>

using namespace std;

int main()
{
    vector<int> p = {10, 20, 30, 40, 50};

    int n = p.size() - 1;

    // DP table
    vector<vector<int>> dp(n, vector<int>(n, 0));

    // Fill the table
    for (int length = 2; length <= n; length++)
    {
        for (int i = 0; i <= n - length; i++)
        {
            int j = i + length - 1;

            dp[i][j] = INT_MAX;

            for (int k = i; k < j; k++)
            {
                int cost = dp[i][k]
                         + dp[k + 1][j]
                         + p[i] * p[k + 1] * p[j + 1];

                if (cost < dp[i][j])
                {
                    dp[i][j] = cost;
                }
            }
        }
    }

    cout << "Minimum number of multiplications = "
         << dp[0][n - 1] << endl;

    return 0;
}
