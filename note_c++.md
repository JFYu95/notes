## Vector

1. 构造函数

   ```c++
   vector<int> obj;//创建一个空的向量存储容器 int
   vector<int> obj(5);//创建一个元素为5的容器
   vector<int> obj(5, 1);//创建一个元素为5的容器,值均为1
   int a[] = {1,2,3,4,5};
   vector<int> obj(a,a+5);
       
   vector<vector<int> > a;//二维数组
   ```

2. 增加函数

   ```c++
   void push_back(const T& x);
   iterator insert(iterator it,const T& x);//向量中迭代器指向元素前增加一个元素x
   
   obj.push_back(4);
   obj.insert(it, 5);
   ```

3. 删除函数

   ```c++
   iterator erase(iterator it);//删除向量中迭代器指向元素
   void pop_back();//删除向量中最后一个元素
   void clear();//清空向量中所有元素
   
   obj.pop_back();//无返回值，如需要该元素，需在pop前获取
   ```


4. 其他

   ```
   n = obj.size();
   obj.resize(10);
   sort(obj.begin(),obj.end());
   sort(obj.rbegin().obj.rend());
   ```

## Map

1. 构造函数

   ```c++
   map<int, int> m;
   ```

2. 插入

   ```
   m[key] = value;
   ```

3. 查找

   ```
   m.find(aim) != m.end() //aim存在 
   ```


## 链表

1. struct

   ```c++
   struct ListNode{
       int val;
       ListNode *next;
       ListNode() : val(0), next(nullptr) {}
       ListNode(int x) : val(x), next(nullptr) {}
       ListNode(int x, ListNode* next) : val(x), next(next) {}
   };
   ```

2. 初始化

   ```c++
   ListNode* t = new ListNode(1);
   ListNode* head = new ListNode(0, t);
   ```

   

## 其他

```c++
//判断int型是否溢出 INT_MAX INT_MIN
long a = 1<<32;
if (a>INT_MAX)
    cout<<"溢出"<<endl;
```

