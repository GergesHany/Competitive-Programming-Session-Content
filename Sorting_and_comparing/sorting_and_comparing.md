# Sorting and comparing 
## session 
- [session](https://drive.google.com/file/d/18maCQBENZY-SYXJJO4hOHjORPDxJjC65/view?usp=sharing)
## sorting vectors 

### sort vectors using sort() function :
Time Complexity: O(nlogn)
```cpp
vector < int > vec = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
sort(vec.begin(), vec.end()); // sort the vector in ascending order
```
you can use the greater and less operator to choose which order do you prefer but as defult ```sort()``` uses less operator.
```cpp
sort(vec.begin(), vec.end(), less < int > ()); // sort the vector in ascending order
```
```cpp
sort(vec.begin(), vec.end(), greater < int > ()); // sort the vector in descending order 
```


### sort vectors using boolen function :
```cpp
bool cmp(int &a, int &b){
  return a > b; // sort in descending order
}
```
```cpp
bool cmp(int &a, int &b){
  return a < b; // sort in ascending order
}
```
now you can use your own function as an operator insted of less and greater 
```cpp
sort(vec.begin(), vec.end(), cmp);
```


### sort vector using lambda Expression :
```cpp
sort(vec.begin(), vec.end(), [](int a, int b) { return a > b; }); // sort the vector in descending order using lambda function
```
```cpp
sort(vec.begin(), vec.end(), [](int a, int b) { return a < b; }); // sort the vector in ascending order using lambda function
```


### articles 
- [Sorting with lambda](https://codeforces.com/blog/entry/92918)

- [Sorting a vector](https://www.geeksforgeeks.org/sorting-a-vector-in-c/)

### problem to solve 
- [Developing Skills](https://codeforces.com/contest/581/problem/C)


## sorting vector of pairs


### sort uing sort() function:
```cpp
sort(vec.begin(), vec.end(), less<pair<int, int>>()); // sort by first element less is default

sort(vec.begin(), vec.end(), greater<pair<int, int>>()); // sort by first element in descending order
```


### sort using boolen function :
```cpp
bool cmp(pair<int, int> &a, pair<int, int> &b){
    return a.second < b.second; // sort in ascending order by second element
}
```
```cpp
sort(vec.begin(), vec.end(), cmp); // sort by second element with function
```

### sort using lambda expression :
```cpp
sort(vec.begin(), vec.end(), [](auto &left, auto &right) { // sort by second element with lambda expression
    return left.second < right.second;
  });
```
```cpp
sort(vec.begin(), vec.end(), [](auto &left, auto &right) {   // sort by first element and then by second element with lambda function
    if (left.first == right.first) return left.second < right.second; 
    return left.first < right.first; 
  });
```


### articles 
- [sorting list using lambda](https://stackoverflow.com/questions/22281962/c11-sorting-list-using-lambda)

- [Sort Vector of Pairs](https://www.geeksforgeeks.org/sort-vector-of-pairs-in-ascending-order-in-c/)



## sorting vector of struct


### sort using operator method :
```cpp
struct data{
    int x;
    bool operator< (const int & a) const{
        return x < a;
    }
};
```
```cpp
vector < data > arr = {1, 2, 3};
sort(arr.begin() , arr.end());
```


### sort using boolen function :
```cpp
// sort The vector with cmp function
bool cmp(data const & lhs, data const & rhs){
  return lhs.val < rhs.val;
}

```
```cpp
vector < data > arr = {1, 2, 3};
sort(arr.begin() , arr.end() , cmp);
```

### sort using lambda expression :
```cpp
// sort The vector with lambda expression
sort(vec.begin(), vec.end(), [](data const & lhs, data const & rhs){
    return lhs.val < rhs.val; 
});
```
### articles 
- [Structure Sorting](https://www.geeksforgeeks.org/structure-sorting-in-c/)

- [Getting Started with Structs Sorting in C++](https://www.section.io/engineering-education/getting-started-with-structs-sorting-in-c++/)

### problem to solve 
- [ Camp Cup](https://codeforces.com/group/vHdLQHscPA/contest/363025/problem/D)


## sorting sets 


### sort using struct :
```cpp
struct value{
  ll val;
  value(ll _value = 0) : val(_value) {}

  // set < val > st;
  bool operator < (value const & rhs) const{
    return val < rhs.val;
  }

  // set < ll, val > st; 
  bool operator () (value const lhs, value const rhs) const {
         return lhs.val > rhs.val;
  } 

};
```
```cpp
  set < value > st; 
  for (int i = 0; i < 10; i++) st.insert(value(i)); 
  for (auto it : st) cout << it.val << " "; cout << "\n";
  // output :  0 1 2 3 4 5 6 7 8 9
  set < ll, value > st2;
  for (int i = 0; i < 10; i++) st2.insert(i);
  for (auto it : st2) cout << it << " "; cout << "\n";
  // output : 9 8 7 6 5 4 3 2 1 0
```


### sort using class :
```cpp
class sorting{

  public:
    int val;

    sorting(int val){
      this->val = val;
    }

    bool operator < (const sorting &other) const{
      return val < other.val;
    }
};
```
```cpp
  set < sorting > s;
  for (int i = 0; i < 10; i++) s.insert(sorting(i));
  for (auto x : s) cout << x.val << " ";
  // output: 0 1 2 3 4 5 6 7 8 9
```


### problem to solve 
- [Camp Cup]( https://codeforces.com/group/vHdLQHscPA/contest/363025/problem/D)


## sorting maps 

### sort using struct :
```cpp
struct value{
  ll val;
  value(ll _value = 0) : val(_value) {}

  //  map < value, ll > mp;
  bool operator < (value const & rhs) const{
    return val < rhs.val;
  }

  //  map < ll, ll, value > mp;
  bool operator () (value const lhs, value const rhs) const {
         return lhs.val > rhs.val;
  } 

};
```
```cpp
  map < value, ll > mp;
  for (int i = 0; i < 5; i++) mp[value(i)]++;
  for (auto it : mp) cout << it.first.val << " " << it.second << "\n";
  //output : 0 1
  //         1 1
  //         2 1
  //         3 1
  //         4 1
  map < ll, ll, value > mp2;
  for (int i = 0; i < 5; i++) mp2[i]++;
  for (auto it : mp2) cout << it.first << " " << it.second << "\n";
  //output :4 1
  //        3 1
  //        2 1
  //        1 1
  //        0 1
```
### sort using vector of pairs :
```cpp
  map < int, int > mp;
  for (int i = 0; i < 5; i++) mp[i]++;

  vector < pair < int, int > > vec;
  for (auto it : mp) vec.push_back(it);
```
and then you can sort the vector with any method you want form here : 
- [ sorting vector of pairs](#sort-using-boolen-function)


## sorting priority_queue :


### sort suing struct :
```cpp
struct value{
  int val;
  bool operator < (const value &other) const{
    return val > other.val;
  }
};
```
```cpp
  priority_queue < value > pq;
  for (int i = 0 ; i < 10; i++) pq.push({i});

  while (!pq.empty()){
    cout << pq.top().val << " ";
    pq.pop();
  }
  //output : 0 1 2 3 4 5 6 7 8 9
```
### articles
- [STL Priority Queue for Structure](https://www.geeksforgeeks.org/stl-priority-queue-for-structure-or-class/)


### problem to solve 
- [Potions (Hard Version)](https://codeforces.com/problemset/problem/1526/C2)

## sorting and comparing sheet
- [icpc scu sheet](https://codeforces.com/group/KQlzWufN6x/contest/376254)

- [icpc assuit sheet](https://codeforces.com/group/c3FDl9EUi9/contest/262795)

## aditional problems :
- [Tea Party](https://codeforces.com/contest/808/problem/C)

- [ Developing Skills](https://codeforces.com/contest/581/problem/C)

- [Standing](https://codeforces.com/group/9NtbQhygks/contest/392258/problem/G)

- [Scoreboard Arrangement](https://codeforces.com/group/9NtbQhygks/contest/389458/problem/F)

- [top k frequent words]( https://leetcode.com/problems/top-k-frequent-words/)

- [the number of weak characters in the game]( https://leetcode.com/problems/the-number-of-weak-characters-in-the-game/)
- [Not a Cheap String](https://codeforces.com/contest/1702/problem/D)


