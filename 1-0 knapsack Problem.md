---


---

<blockquote>
<p><em>Best examples</em></p>
<p><strong>Easy</strong> - <a href="https://leetcode.com/problems/coin-change/discuss/121814/C++-Dynamic-Programming-%28Knapsack-Approach%29">Coin Change 1</a> ,<a href="https://leetcode.com/problems/coin-change-2/discuss/121863/C++-Dynamic-Programming-Solution-%28Knapsack-Approach%29">Coin change 2<br>
</a><br>
<strong>Medium</strong> - <a href="https://leetcode.com/problems/ones-and-zeroes/discuss/121876/C++-DP-Knapsack-Approach">0s &amp; 1s</a></p>
</blockquote>
<p>Template : <em>Wth the constaint W , we need to maximize the V</em></p>
<pre><code>int knapsack(int val[], int wt[], int n, int W)
{
   int dp[n+1][W+1];
   memset(dp, 0, sizeof dp);
   for (int i = 1; i &lt;= n; i++)
   {
       for (w = 1; w &lt;= W; w++)
       {
           dp[i][w] = dp[i-1][w];  //don't include the item
           if (wt[i-1] &lt;= w)
                 dp[i][w] = max(dp[i][w], 
                           val[i-1] + dp[i-1][w-wt[i-1]]);  
       }
   }
   return dp[n][W];
}
</code></pre>

