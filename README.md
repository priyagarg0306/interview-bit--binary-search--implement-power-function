# interview-bit--binary-search--implement-power-function

------> Question:

Implement pow(x, n) % d.
In other words, given x, n and d,

find (xn % d)

Note that remainders on division cannot be negative. In other words, make sure the answer you return is non negative.



Problem Constraints
-109 <= x <= 109
0 <= n <= 109
1 <= d <= 109


Example Input
x = 2
n = 3
d = 3


Example Output
2


Example Explanation
23 % 3 = 8 % 3 = 2.


-----> Code:

#define ll long long

int Solution::pow(int x, int n, int d) {

    if(x==0){
        return 0;
    }
    
    ll res=1,a=x;

    while(n>0){
        if(n%2!=0){
            res=(res*a)%d;
        }

        n=n/2;
        a=(a*a)%d;
    }

    return (d+res)%d;
}
