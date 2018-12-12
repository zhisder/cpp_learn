# 类

## 6 个重要的函数

1. 3 个构造函数，创建类实例时调用。
2. 2 个赋值运算符在对已经存在的对象做“=”操作时调用。
3. 移动构造函数和移动赋值运算符在临时对象的时候调用。

### 1. 默认构造函数

```c++
ClassName();//声明
ClassName::ClassName() body //类外定义
ClassName() = delete;//禁止编译器自动生成默认构造函数
ClassName() = default;//生成默认构造函数

auto v= ClassName();
```

### 2. 复制构造函数

```C++
ClassName( const ClassName& );
ClassName( const ClassName& ) = delete;
ClassName( const ClassName& ) = default;

auto v2(v1);
auto v2 = v1;
```

### 3. 移动构造函数

```C++
ClassName( const ClassName&& );
ClassName( const ClassName&& ) = delete;
ClassName( const ClassName&& ) = default;

auto v3 = v1+v2;//调用加法得到中间数据后，再调用移动构造函数
```

### 4. 复制赋值运算符

```C++
ClassName& ClassName::operator=(ClassName&);
ClassName& ClassName::operator=(ClassName&) = delete;
ClassName& ClassName::operator=(ClassName&) = default;

v2 = v1;
```

### 5. 移动赋值运算符

```C++
ClassName& ClassName::operator=(ClassName&);
ClassName& ClassName::operator=(ClassName&) = delete;
ClassName& ClassName::operator=(ClassName&) = default;

v3 = v1+v2;//调用加法得到中间数据后，再调用移动赋值运算符
```

### 6. 析构函数

变量生存期结束后调用。

```C++
~ClassName();
```
