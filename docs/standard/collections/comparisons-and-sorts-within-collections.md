---
title: "Сравнение и сортировка в коллекциях"
description: "Сравнение и сортировка в коллекциях"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c7b7c005-628d-427a-91ad-af0c3958c00e
translationtype: Human Translation
ms.sourcegitcommit: e07788926a995b41571be276379ad9285747951d
ms.openlocfilehash: de1fe3bb9b9a75561b4f28ec4609491d6f3c39f5

---

# <a name="comparisons-and-sorts-within-collections"></a>Сравнение и сортировка в коллекциях

Классы [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections) выполняют сравнения почти во всех процессах управления коллекциями — будь то поиск элемента для удаления или возвращение значения пары "ключ-значение".

В коллекциях обычно используется компаратор проверки на равенство и (или) компаратор упорядочения. Для сравнения используются две конструкции. 

## <a name="checking-for-equality"></a>Проверка на равенство

Такие методы, как `Contains`, `IndexOf`, `LastIndexOf` и `Remove`, используют компаратор проверки на равенство для элементов коллекции. Если коллекция является универсальной, то элементы проверяются на равенство согласно следующим правилам.

*   Если тип T реализует универсальный интерфейс [IEquatable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IEquatable-1), компаратором проверки на равенство является метод `Equals` этого интерфейса.

*   Если тип T не реализует `IEquatable<T>`, используется `Object.Equals`.

Кроме того, некоторые перегрузки конструктора для коллекций словаря принимают реализацию [IEqualityComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEqualityComparer-1), которая используется для сравнения ключей на равенство.

## <a name="determining-sort-order"></a>Определение порядка сортировки

Такие методы, как `BinarySearch` и `Sort`, используют компаратор упорядочения для элементов коллекции. Сравнение может проводиться между элементами коллекции или между элементом и заданным значением. Для сравнения объектов существуют понятия "компаратор по умолчанию" и "явный компаратор". 

Для реализации интерфейса `IComparable` компаратор по умолчанию использует по крайней мере один из сравниваемых объектов. Интерфейс `IComparable` рекомендуется реализовать во всех классах, используемых в качестве значений в коллекциях списков или в качестве ключей в коллекциях словарей. В универсальной коллекции сравнение на равенство определяется в соответствии со следующими правилами.

*   Если тип T реализует универсальный интерфейс [System.IComparable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IComparable-1), компаратором по умолчанию является метод `CompareTo(T)` этого интерфейса.

*   Если тип T реализует универсальный интерфейс [System.IComparable](https://docs.microsoft.com/dotnet/core/api/System.IComparable), компаратором по умолчанию является метод `CompareTo`(Object) этого интерфейса.

*   Если тип T не реализует никакого интерфейса, компаратор по умолчанию отсутствует, а компаратор или делегат сравнения должен быть предоставлен явно.

Для осуществления явных сравнений некоторые методы принимают реализацию `IComparer` в качестве параметра. Например, метод `List<T>.Sort` принимает реализацию [System.Collections.Generic.IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1). 

## <a name="equality-and-sort-example"></a>Пример сортировки и проверки на равенство

В следующем примере демонстрируется реализация [IEquatable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IEquatable-1) и [IComparable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IComparable-1) в простом бизнес-объекте. Кроме того, когда объект сохраняется в списке и сортируется, вы увидите, что вызов метода `Sort()` приведет к использованию компаратора по умолчанию для типа "Part", а метод `Sort(Comparison<T>)` будет реализован с помощью анонимного метода.

C#

```csharp
using System;
using System.Collections.Generic;
// Simple business object. A PartId is used to identify the type of part 
// but the part name can change. 
public class Part : IEquatable<Part> , IComparable<Part>
{
    public string PartName { get; set; }

    public int PartId { get; set; }

    public override string ToString()
    {
        return "ID: " + PartId + "   Name: " + PartName;
    }
    public override bool Equals(object obj)
    {
        if (obj == null) return false;
        Part objAsPart = obj as Part;
        if (objAsPart == null) return false;
        else return Equals(objAsPart);
    }
    public int SortByNameAscending(string name1, string name2)
    {

        return name1.CompareTo(name2);
    }

    // Default comparer for Part type.
    public int CompareTo(Part comparePart)
    {
          // A null value means that this object is greater.
        if (comparePart == null)
            return 1;

        else
            return this.PartId.CompareTo(comparePart.PartId);
    }
    public override int GetHashCode()
    {
        return PartId;
    }
    public bool Equals(Part other)
    {
        if (other == null) return false;
        return (this.PartId.Equals(other.PartId));
    }
    // Should also override == and != operators.

}
public class Example
{
    public static void Main()
    {
        // Create a list of parts.
        List<Part> parts = new List<Part>();

        // Add parts to the list.
        parts.Add(new Part() { PartName = "regular seat", PartId = 1434 });
        parts.Add(new Part() { PartName= "crank arm", PartId = 1234 });
        parts.Add(new Part() { PartName = "shift lever", PartId = 1634 }); ;
        // Name intentionally left null.
        parts.Add(new Part() {  PartId = 1334 });
        parts.Add(new Part() { PartName = "banana seat", PartId = 1444 });
        parts.Add(new Part() { PartName = "cassette", PartId = 1534 });


        // Write out the parts in the list. This will call the overridden 
        // ToString method in the Part class.
        Console.WriteLine("\nBefore sort:");
        foreach (Part aPart in parts)
        {
            Console.WriteLine(aPart);
        }


        // Call Sort on the list. This will use the 
        // default comparer, which is the Compare method 
        // implemented on Part.
        parts.Sort();


        Console.WriteLine("\nAfter sort by part number:");
        foreach (Part aPart in parts)
        {
            Console.WriteLine(aPart);
        }

        // This shows calling the Sort(Comparison(T) overload using 
        // an anonymous method for the Comparison delegate. 
        // This method treats null as the lesser of two values.
        parts.Sort(delegate(Part x, Part y)
        {
            if (x.PartName == null && y.PartName == null) return 0;
            else if (x.PartName == null) return -1;
            else if (y.PartName == null) return 1;
            else return x.PartName.CompareTo(y.PartName);
        });

        Console.WriteLine("\nAfter sort by name:");
        foreach (Part aPart in parts)
        {
            Console.WriteLine(aPart);
        }

        /*

            Before sort:
        ID: 1434   Name: regular seat
        ID: 1234   Name: crank arm
        ID: 1634   Name: shift lever
        ID: 1334   Name:
        ID: 1444   Name: banana seat
        ID: 1534   Name: cassette

        After sort by part number:
        ID: 1234   Name: crank arm
        ID: 1334   Name:
        ID: 1434   Name: regular seat
        ID: 1444   Name: banana seat
        ID: 1534   Name: cassette
        ID: 1634   Name: shift lever

        After sort by name:
        ID: 1334   Name:
        ID: 1444   Name: banana seat
        ID: 1534   Name: cassette
        ID: 1234   Name: crank arm
        ID: 1434   Name: regular seat
        ID: 1634   Name: shift lever

         */

    }
}
```

## <a name="see-also"></a>См. также

[IComparer](https://docs.microsoft.com/dotnet/core/api/System.Collections.IComparer)

[IEquatable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IEquatable-1)

[IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1)

[IComparable](https://docs.microsoft.com/dotnet/core/api/System.IComparable)

[IComparable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.IComparable-1)



<!--HONumber=Nov16_HO1-->


