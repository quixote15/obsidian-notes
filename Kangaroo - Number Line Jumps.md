---
share: true
---

This is a classic problem known as the Kangaroo Problem. You have to figure out a way to get both kangaroos at the same location at the same time as part of the show. If it is possible, return YES, otherwise return NO.


- The first kangaroo starts at location and moves at a rate of- meters per jump.
- The second kangaroo starts at location
  and moves at a rate of meters per jump.

This is a [Hackerhank problem](https://www.hackerrank.com/challenges/kangaroo/problem?isFullScreen=true) I solved


![[Pasted image 20230928061128.png]]


The C++ code uses an iterative approach to simulate the kangaroos' movements. It checks if they start at the same position, returning "YES" if they do. Otherwise, it iterates up to a limit of 10,000 times, advancing the kangaroos' positions based on their speeds. If they meet during this process, it returns "YES"; otherwise, it returns "NO" after the iterations. This approach ensures a bounded execution and provides a solution to the kangaroo problem.

Heres a Pseudocode:
```
function kangaroo(x1, v1, x2, v2):
    jump_limit = 10000
    
    if isSamePosition(x1, x2) then
        return "YES"

    for i from 1 to jump_limit do
        x1 = x1 + v1
        x2 = x2 + v2

        if isSamePosition(x1, x2) then
            return "YES"

    return "NO"
    
function isSamePosition(x1, x2):
    return x1 == x2

```

C++20 Code:
```cpp
#include <bits/stdc++.h>

  

using namespace std;

  

string ltrim(const string &);

string rtrim(const string &);

vector<string> split(const string &);

  

/*

* Complete the 'kangaroo' function below.

*

* The function is expected to return a STRING.

* The function accepts following parameters:

* 1. INTEGER x1

* 2. INTEGER v1

* 3. INTEGER x2

* 4. INTEGER v2

*/

  
  

bool isSamePos(int x1, int x2) {

return x1 == x2;

}

  

string kangaroo(int x1, int v1, int x2, int v2) {

const int jump_limit = 10000;

if(isSamePos(x1, x2)) return "YES";

for(int i = 0; i < jump_limit; i++) {

x1 += v1;

x2 += v2;

if(isSamePos(x1, x2)) return "YES";

}

return "NO";

}

  

int main()

{

ofstream fout(getenv("OUTPUT_PATH"));

  

string first_multiple_input_temp;

getline(cin, first_multiple_input_temp);

  

vector<string> first_multiple_input = split(rtrim(first_multiple_input_temp));

  

int x1 = stoi(first_multiple_input[0]);

  

int v1 = stoi(first_multiple_input[1]);

  

int x2 = stoi(first_multiple_input[2]);

  

int v2 = stoi(first_multiple_input[3]);

  

string result = kangaroo(x1, v1, x2, v2);

  

fout << result << "\n";

  

fout.close();

  

return 0;

}

  

string ltrim(const string &str) {

string s(str);

  

s.erase(

s.begin(),

find_if(s.begin(), s.end(), not1(ptr_fun<int, int>(isspace)))

);

  

return s;

}

  

string rtrim(const string &str) {

string s(str);

  

s.erase(

find_if(s.rbegin(), s.rend(), not1(ptr_fun<int, int>(isspace))).base(),

s.end()

);

  

return s;

}

  

vector<string> split(const string &str) {

vector<string> tokens;

  

string::size_type start = 0;

string::size_type end = 0;

  

while ((end = str.find(" ", start)) != string::npos) {

tokens.push_back(str.substr(start, end - start));

  

start = end + 1;

}

  

tokens.push_back(str.substr(start));

  

return tokens;

}
```


PLUS: Here's a recursive version of my code:


```cpp
string kangaroo(int x1, int v1, int x2, int v2) {
    if (x1 == x2) {
        return "YES";
    }

    if (x1 < x2 && v1 <= v2) {
        return "NO";
    }

    if (x1 > x2 && v1 >= v2) {
        return "NO";
    }

    return kangaroo(x1 + v1, v1, x2 + v2, v2);
}

```