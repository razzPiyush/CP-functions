#include <bits/stdc++.h>
#define int long long
#define fi first
#define se second
#define Radhe ios_base:: sync_with_stdio(false); cin.tie(NULL);
#define krishna cout.tie(NULL);
using namespace std;
typedef long double ld;
const int MAX=1000001;
/**********************************to find x^n***********************************************/
//O(n)
//pow(x,n) have time complexity of logn.
int power(int x, int n)
{
    if(n==0){
        return 1;
    }
    return x*power(x, n-1);
}
/**********************************to find factorial(n)%m**************************************/
//o(n)
int fact[MAX];
int m= 1e9+7;
void pre()
{
    fact[0]=1;
    for(int i=1; i<MAX; i++)
    {
        fact[i]= fact[i-1]*i; // since m>1e6 we will not care for i%m
        fact[i]= fact[i]%m;
    }
}
/***********************************to fin (n!)********************************************/
int factorial (int n, int m)
{
    if(n==0){
        return 1;
    }
    return n*factorial(n-1,m);
}
/**********************************to find (x^n)%m********************************************/
//O(logn)
int binExp (int x, int n, int m) 
{
    if(n==0){
        return 1;
    }
    if(n%2==0){
        return binExp(((x%m)*(x%m))%m, n/2, m);
    }
    return ((x%m)*(binExp(((x%m)*(x%m))%m, (n-1)/2, m)))%m;
} 
/********************************sieve of earthrones********************************************/
//O(nlog(logn))
/*
    bool is_prime[MAX];
    for(int i=0; i<MAX; i++)
    {
        is_prime[i]=1;
    }
    is_prime[0]=0;
    is_prime[1]=0;
    for(int i=2; i*i<MAX; i++)
    {
        if(is_prime[i]==1){
            for(int j=i*i; j<MAX; j+=i)
            {
                is_prime[j]=0;
            }
        }
    }
*/
/******************************smallest prime factor [SPF]***************************************/
//O(nlog(logn))
/*
    int spf[MAX];
    for(int i=0; i<MAX; i++)
    {
        spf[i]=i;
    }
    for(int i=2; i*i<MAX; i++)
    {
        if(spf[i]==i){
            for(int j=i*i; j<MAX; j+=i)
            {
                if(spf[j]==j){
                    spf[j]=i;
                }
            }
        }
    }
*/
/*******************************Euler Totient Function [ETF]*************************************/
/*
phi(n) = count of numbers from 1 to n that are coprime with n.
Coprime:- 2 numbers x and y are coprime if gcd(x,y)=1.
phi (2)=1 (1)
phi(4)=2 (1,3)
phi(8)=4 (1,3,5,7)
phi(p^k) = p^k-p^(k-1)
N = (p1^k1).(p2^k2)....
Where p1,p2,... are prime numbers.
phi(a*b) = phi(a).phi(b) if a and b are coprime.
*/
/*
    int phi[MAX];
    for(int i=0; i<MAX; i++)
    {
        phi[i]=i;
    }
    for(int i=2; i*i<MAX; i++)
    {
        if(phi[i]==i){
            for(int j=i*i;  j<MAX; j+=i)
            {
                phi[j]= phi[j]- phi[j]/i;
            }
        }
    }
*/
/********************************segmented seive************************************************/
// (r-l) * log log (r)
void segmented_sieve ()
{
    int l = 1e9, r = 1e9 + 10;
    int n = sqrtl(r) + 2;
    // find all primes <= n
    vector<int> primes;
    vector<bool> isprime(n, true);
    for (int i = 2; i * i < n; i++)
    {
        if (isprime[i]!=1){
            continue;
        }
        primes.push_back(i);
        for (int j = i * i; j < n; j += i)
        {
            isprime[j] = 0;
        }
    }
    vector<bool> isprimeSeg(r - l + 1, true);
    for (int p : primes)
    {
        for (int i = max(p * p, ((l + p - 1) / p) * p); i <= r; i += p)
        {
            isprimeSeg[i-l] = false;
        }
    }
    for (int i = 0; i < r-l+1; i++)
    {
        if (isprimeSeg[i]==1){
            cout << i + l << " ";
        }
    }
    cout<<endl;
}
/************************************nCr********************************************************/
int nCr (int n, int r, int m)
{
    //nCr= fact[n]*fact[r]^-1*fact[n-r]^-1
    int temp1= fact[n];  // fact[n] is basicaly factorial of n by mod m
    int temp2= fact[r]*fact[n-r];
    temp2= temp2%m;
    int temp3 = binExp(temp2, m-2, m); // a^-1%m = a^(m-2)%m
    temp1= (temp1*temp3)%m;
    return temp1;
}
/**********************************deca to binary***********************************************/
string decaToBin (int n)
{
    string x="";
    for(int i=31; i>=0; i--)
    {
        if(n&(1<<i)){
            x += '1';
        }
        else{
            x += '0';
        }
    }
    return x;
}
/********************************binary to deca************************************************/
int binToDeca (string x)
{
    int ans=0;
    int j=0;
    for(int i=31; i>=0; i--)
    {
        if(x[i]=='1'){
            ans += pow(2,j);
        }
        j++;
    }
    return ans;
}
/**********************************************************************************************/
int32_t main()
{
    Radhe krishna;
    
    return 0;
}
