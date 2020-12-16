## Vector

1. 构造函数

   ```c++
   vector<int> obj;//创建一个空的向量存储容器 int
   vector<int> obj(5);//创建一个元素为5的容器
   vector<int> obj(5, 1);//创建一个元素为5的容器,值均为1
   int a[] = {1,2,3,4,5};
   vector<int> obj(a,a+5);
   vector<int> obj({1,2,3,4,5,6});
       
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

   ```c++
   m[key] = value;
   ```

3. 查找

   ```c++
   m.find(aim) != m.end() //aim存在 
   ```

4. 注：
   * map的key（int or string）自带排序，使用`for(auto it=m.begin();it!=m.end();it++){}`即可
   * 

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


## Stack

1. 初始化

   ```c++
   stack<int> stk;
   ```

2. 成员函数

   ```c++
   stk.size() //返回栈中元素个数
   stk.top() //返回栈顶的元素
   stk.pop() //从栈中取出并删除元素, 注:返回类型为void
   stk.push(e) //向栈中添加元素e
   stk.empty() //栈为空时返回true
   ```


## 二分法

1. 写法

   ```c++
   //注意while的条件，以及移动左右边界的方式，需匹配，否则会漏掉某些查找
   int left = 0;
   int right = nums.size()-1;
   int mid;
   while(left<=right){
       mid = (left+right)>>1;
       if (/*查找到的情况*/){
           //...
       }
       else if(/*移动左边界*/){
   		left = mid+1;
       }
       else(/*移动右边界*/){
           right = mid-1;
       }
   }
   ```


## 深搜

1. 写法

   ```c++
   int deep_find(int a, int b)
   {
       //特殊情况判断
       //初始化所需变量
       int c,d,e;
       //一些操作...
       find(c,d,e);
       return e;
   }
   void find(int c,int d,int e)
   {
       //返回条件，到达叶子结点
       if(/**/){
           //...
       }
       //搜索宽度
       for(){
           //剪枝条件
           if(/**/){
               break;
           }
           //一些操作
           find(/**/);
           //注意返回到原来的状态，以进入for循环下一轮
       }
       return;
   }
   ```

   

## 其他

```c++
//判断int型是否溢出 INT_MAX INT_MIN
long a = 1<<32;
if (a>INT_MAX)
    cout<<"溢出"<<endl;

//数组长度
int a[] = {2,32,4,3,4,45};
int n = sizeof(a)/sizeof(a[0]);

//取绝对值
int a = -9;
double b = -8.999;
int aa = abs(a);
double bb = abs(b);

//array vector查找
#include <algorithm>
int a[] = {2,3,4,5,6};
vector<int> vec(a,a+5);
if (find(vec.begin(),vec.end(),4)!=vec.end())
    return true;
else
    return false;
//返回下标
auto aim = find(vec.begin(),vec.end(),4);
return aim-vec.begin();

//注意引用的用法
//&符号只用在初始化（等号左侧，尽量与参数类型合用，以免出错）和函数形参中，其他地方只需用原变量名即可，否则与&取地址符号（尽量与变量名合用）混淆。

vector<vector<int> > res;
vector<int> c({1,2,3,4});
//需注意res为开辟的实际存储空间，而不是存放的地址
//因此
res.push_back(c);
//push_back()函数为复制原变量，并存放到操作对象的存储空间中，根据vector特性，若空间不足则扩大。
//所以push_back()操作已包含复制，需要与python做区别。

//删除vector中重复的元素
sort(c.begin(), c.end());
T::iterator new_end = unique(c.begin(), c.end());//"删除"相邻的重复元素
c.erase(new_end, c.end());//删除(真正的删除)重复的元素
```

