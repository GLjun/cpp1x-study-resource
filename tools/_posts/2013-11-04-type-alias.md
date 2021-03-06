---
layout : post
title : "类型别名"
category : "Language"
---

有两种方法可用于定义类型别名，第一种方法是使用`typedef`关键字，这个C++03就已经支持了。第二种方式是使用C++11新的声明方式`using`关键字。方法很简单，比如：

    using MyUint = unsigned int;

那么 MyUint 和 unsigned int 等价了。

随即，你可能想到了一个问题：`typedef`和`using`的区别在哪里?

我找了一个sof的帖子:[Difference between typedef and C++11 type alias [duplicate]](http://stackoverflow.com/questions/18287151/difference-between-typedef-and-c11-type-alia)

> There is absolutely no difference between both.
> 
> If you take a look at the standard :
> 
> 7.1.3 The typedef speciﬁer [dcl.typedef ]
> 
> A typedef-name can also be introduced by an alias-declaration. The identifier following the using keyword becomes a typedef-name. It has the same semantics as if it were introduced by the typedef specifier. In particular, it does not define a new type and it shall not appear in the type-id.
> 
> 7.3.3 The using declaration [namespace.udecl]
> 
> If a using-declaration uses the keyword typename and specifies a dependent name (14.6.2), the name introduced by the using-declaration is treated as a typedef-name.
> 
> However from this page : http://en.cppreference.com/w/cpp/language/type_alias
> 
> It is said :
> 
> Type aliases are similar to typedefs, however, have the advantage of working with templates.
> 
> It is seems that this :
> 
> // template type alias
> template<class T> using ptr = T*;
> // the name 'ptr<T>' is now an alias for pointer to T
> ptr<int> x;
> Is only possible with the using directive.
> 
> And do not forget that this is a C++11 feature. Some compilers do not support it yet.

我想，上面的这段回复足够回答你的问题了。
