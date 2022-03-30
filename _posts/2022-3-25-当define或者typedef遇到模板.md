```cpp
template<class T>
typedef struct NODE
{
	T data;
	struct NODE *next;
} LinkList;
```

这里的代码会报错，因为define和typedef不允许定义模糊的类型，如果要使用，一定要显式指明数据类型。

```cpp
template<class T>
struct NODE
{
	T data;
	struct NODE *next;
};
typedef NODE<int> LinkList;
```

上面为正确的用法，并且对于typedef必须定义在模板结构的下面。