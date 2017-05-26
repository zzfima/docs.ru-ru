---
title: "Вариативность в универсальных интерфейсах (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 7acde09659624fd097471824e6407dc181d88893
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="variance-in-generic-interfaces-c"></a>Вариативность в универсальных интерфейсах (C#)
В платформе .NET Framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов. Поддержка вариативности позволяет выполнять неявное преобразование классов, реализующих эти интерфейсы. Сейчас вариативными являются следующие интерфейсы.  
  
-   <xref:System.Collections.Generic.IEnumerable%601> (T является ковариантным)  
  
-   <xref:System.Collections.Generic.IEnumerator%601> (T является ковариантным)  
  
-   <xref:System.Linq.IQueryable%601> (T является ковариантным)  
  
-   <xref:System.Linq.IGrouping%602> (`TKey` и `TElement` являются ковариантными)  
  
-   <xref:System.Collections.Generic.IComparer%601> (T является контравариантным)  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601> (T является контравариантным)  
  
-   <xref:System.IComparable%601> (T является контравариантным)  
  
 Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в параметре универсального типа интерфейса. Чтобы продемонстрировать функцию ковариации, рассмотрим следующие универсальные интерфейсы: `IEnumerable<Object>` и `IEnumerable<String>`. Интерфейс `IEnumerable<String>` не наследует интерфейс `IEnumerable<Object>`. При этом тип `String` наследует тип `Object`, и в некоторых случаях может потребоваться назначить объекты этих интерфейсов друг другу. Это показано в следующем примере кода.  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 В более ранних версиях .NET Framework этот код приводит к ошибке компиляции в C# в `Option Strict On`. Но теперь можно использовать `strings` вместо `objects`, как показано в предыдущем примере, поскольку интерфейс <xref:System.Collections.Generic.IEnumerable%601> является ковариантным.  
  
 Контравариантность позволяет методу иметь типы аргументов, степень наследования которых меньше, чем указано в параметре универсального типа интерфейса. Чтобы продемонстрировать функцию контравариантности, предположим, что создан класса `BaseComparer` для сравнения экземпляров класса `BaseClass`. Класс `BaseComparer` реализует интерфейс `IEqualityComparer<BaseClass>`. Поскольку теперь интерфейс <xref:System.Collections.Generic.IEqualityComparer%601> является контравариантным, для сравнения экземпляров классов, наследующих класс `BaseClass`, можно использовать класс `BaseComparer`. Это показано в следующем примере кода.  
  
```csharp  
// Simple hierarchy of classes.  
class BaseClass { }  
class DerivedClass : BaseClass { }  
  
// Comparer class.  
class BaseComparer : IEqualityComparer<BaseClass>   
{  
    public int GetHashCode(BaseClass baseInstance)  
    {  
        return baseInstance.GetHashCode();  
    }  
    public bool Equals(BaseClass x, BaseClass y)  
    {  
        return x == y;  
    }  
}  
class Program  
{  
    static void Test()  
    {  
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();  
  
        // Implicit conversion of IEqualityComparer<BaseClass> to   
        // IEqualityComparer<DerivedClass>.  
        IEqualityComparer<DerivedClass> childComparer = baseComparer;  
    }  
}  
```  
  
 Дополнительные примеры см.в разделе [Использование вариативности в интерфейсах для универсальных коллекций (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).  
  
 Вариативность в универсальных интерфейсах поддерживается только для ссылочных типов. Типы значений не поддерживают вариативность. Например, `IEnumerable<int>` нельзя неявно преобразовать в `IEnumerable<object>`, так как типом значения является integer.  
  
```csharp  
IEnumerable<int> integers = new List<int>();  
// The following statement generates a compiler errror,  
// because int is a value type.  
// IEnumerable<Object> objects = integers;  
```  
  
 Кроме того, важно помнить, что классы, которые реализуют вариативные интерфейсы, сами являются инвариантными. Например, несмотря на то, что <xref:System.Collections.Generic.List%601> реализует ковариантный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, неявно преобразовать `List<Object>` в `List<String>` нельзя. Это показано в следующем примере кода.  
  
```csharp  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a>См. также  
 [Использование вариативности в интерфейсах для универсальных коллекций (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)   
 [Создание вариативных универсальных интерфейсов (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)   
 [Универсальные интерфейсы](../../../../standard/generics/interfaces.md)   
 [Вариативность в делегатах (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
