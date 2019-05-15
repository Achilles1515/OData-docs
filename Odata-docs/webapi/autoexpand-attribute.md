---
title: "4.15 AutoExpand attribute"
description: ""

ms.date: 08/11/2015
---
# AutoExpand attribute

In OData WebApi 5.7, we can put `AutoExpand` attribute on navigation property to make it automatically expand without `expand` query option, or can put this attribute on class to make all Navigation Property on this class automatically expand.

### Model

```C#
public class Product
{
    public int Id { get; set; }
    [AutoExpand]
    public Category Category { get; set; }
}

public class Category
{
    public int Id { get; set; }
    [AutoExpand]
    public Customer Customer{ get; set; }
}
```

### Result
If you call return Product in response, Category will automatically expand and Customer will expand too. It works the same if you put `[AutoExpand]`on Class if you have more navigation properties to expand.
