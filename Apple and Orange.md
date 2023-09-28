---
share: true
---

The problem involves determining the number of apples and oranges that fall on Sam's house. Given the positions of the house, apple and orange trees, as well as the distances the fruits fall, the task is to count how many of them land within the specified range.

[Link on hackerhank](https://www.hackerrank.com/challenges/apple-and-orange/problem?isFullScreen=true)


***Solution**

That idea is to iterate through the distances of both fruits, calculating their final landing positions relative to their respective trees. If a fruit's position falls within the house's range, it increments the corresponding count. Finally, it prints the counts of apples and oranges that land on Sam's house.

**Pseudocode:**

```
function countApplesAndOranges(s, t, a, b, apples, oranges):
    inRangeApples = 0
    inRangeOranges = 0

    for each appleDistance in apples:
        appleLoc = a + appleDistance
        if appleLoc is in range [s, t]:
            increment inRangeApples

    for each orangeDistance in oranges:
        orangeLoc = b + orangeDistance
        if orangeLoc is in range [s, t]:
            increment inRangeOranges

    output inRangeApples
    output inRangeOranges

```

**C++ Function:**
```cpp
void countApplesAndOranges(int s, int t, int a, int b, vector<int> apples, vector<int> oranges) {
    int inRangeApples = 0;
    int inRangeOranges = 0;

    for(int i = 0; i < apples.size(); i++) {
        int appleLoc = apples[i] + a;
        if(appleLoc >= s && appleLoc <= t) inRangeApples++;
    }

    for(int i = 0; i < oranges.size(); i++) {
        int orangeLoc = oranges[i] + b;
        if(orangeLoc >= s && orangeLoc <= t) inRangeOranges++;
    }

    cout << inRangeApples << endl;
    cout << inRangeOranges << endl;
}

```


My whole c++ hackerhank solution:
```cpp
#include <bits/stdc++.h>

  

using namespace std;

  

string ltrim(const string &);

string rtrim(const string &);

vector<string> split(const string &);

  

/*

* Complete the 'countApplesAndOranges' function below.

*

* The function accepts following parameters:

* 1. INTEGER s

* 2. INTEGER t

* 3. INTEGER a

* 4. INTEGER b

* 5. INTEGER_ARRAY apples

* 6. INTEGER_ARRAY oranges

*/

  

void countApplesAndOranges(int s, int t, int a, int b, vector<int> apples, vector<int> oranges) {

int inRangeApples = 0;

int inRangeOranges = 0;

for(int i = 0; i < apples.size(); i++) {

int appleLoc = apples[i] + a;

if(appleLoc >= s && appleLoc <= t) inRangeApples++;

}

for(int i = 0; i < oranges.size(); i++) {

int appleLoc = oranges[i] + b;

if(appleLoc >= s && appleLoc <= t) inRangeOranges++;

}

cout << inRangeApples << endl;

cout << inRangeOranges << endl;

}

  

int main()

{

string first_multiple_input_temp;

getline(cin, first_multiple_input_temp);

  

vector<string> first_multiple_input = split(rtrim(first_multiple_input_temp));

  

int s = stoi(first_multiple_input[0]);

  

int t = stoi(first_multiple_input[1]);

  

string second_multiple_input_temp;

getline(cin, second_multiple_input_temp);

  

vector<string> second_multiple_input = split(rtrim(second_multiple_input_temp));

  

int a = stoi(second_multiple_input[0]);

  

int b = stoi(second_multiple_input[1]);

  

string third_multiple_input_temp;

getline(cin, third_multiple_input_temp);

  

vector<string> third_multiple_input = split(rtrim(third_multiple_input_temp));

  

int m = stoi(third_multiple_input[0]);

  

int n = stoi(third_multiple_input[1]);

  

string apples_temp_temp;

getline(cin, apples_temp_temp);

  

vector<string> apples_temp = split(rtrim(apples_temp_temp));

  

vector<int> apples(m);

  

for (int i = 0; i < m; i++) {

int apples_item = stoi(apples_temp[i]);

  

apples[i] = apples_item;

}

  

string oranges_temp_temp;

getline(cin, oranges_temp_temp);

  

vector<string> oranges_temp = split(rtrim(oranges_temp_temp));

  

vector<int> oranges(n);

  

for (int i = 0; i < n; i++) {

int oranges_item = stoi(oranges_temp[i]);

  

oranges[i] = oranges_item;

}

  

countApplesAndOranges(s, t, a, b, apples, oranges);

  

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