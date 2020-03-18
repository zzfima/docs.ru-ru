---
title: Обзор универсальных типов (универсальных шаблонов)
description: Сведения о том, как универсальные шаблоны действуют в качестве шаблона кода, позволяющего разработчикам определять типобезопасные структуры данных, не выполняя реальный тип данных.
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 3c1181f5be717f328ae906c6009fc8a34b904c89
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "61923855"
---
# <a name="generic-types-overview"></a>Обзор универсальных типов

Каждый разработчик для .NET постоянно использует универсальные шаблоны, прямо или косвенно. Замечали ли вы, что используете <xref:System.Collections.Generic.IEnumerable%601> при работе с LINQ в C#? Или, может быть, вы замечали, что большинство методов возвращает IQueryable\<T> в примере "универсального репозитория" для обращения к базам данных через Entity Framework? Возможно, вы задавались вопросом, что в этих примерах означает **T** и зачем это нужно.

**Универсальные шаблоны**, которые появились в .NET Framework версии 2.0, представляют собой шаблон кода, позволяющий разработчикам определять [типобезопасные](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) структуры данных, не привязываясь к конкретному типу данных. Например, <xref:System.Collections.Generic.List%601> — это [универсальная коллекция](xref:System.Collections.Generic), которую можно объявить и использовать с любым типом, например `List<int>`, `List<string>`, `List<Person>` и т. д.

Чтобы понять, чем полезны универсальные шаблоны, давайте рассмотрим конкретный пример класса до и после добавления универсальных шаблонов: <xref:System.Collections.ArrayList>. В .NET Framework 1.0 все элементы `ArrayList` имели тип <xref:System.Object>. Это означало, что любой добавленный элемент негласно преобразовывался в `Object`. То же самое происходило и при чтении элементов из списка. Эти процессы называются [упаковка-преобразование и распаковка-преобразование](../csharp/programming-guide/types/boxing-and-unboxing.md), и их использование ухудшает производительность. Более того, у нас нет надежного способа во время компиляции определить тип данных в списке. Это приводит к созданию кода, который неудобно обслуживать. Универсальные шаблоны решают эту проблему, определяя тип данных для каждого экземпляра в списке. Например, вы можете указать, что `List<int>` всегда будет содержать целые числа, а `List<Person>` — объекты Person.

Универсальные шаблоны также используются во время выполнения. Это означает, что среда выполнения знает, какой тип структуры вы используете, что позволяет эффективнее хранить ее в памяти.

В следующем примере приведена небольшая программа, которая демонстрирует преимущества понимания типов структуры данных во время выполнения:

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

Эта программа возвращает приблизительно следующее:

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

Первое, что можно заметить, — сортировка списка с универсальным шаблоном осуществляется значительно быстрее, чем без него. Также видно, что для списка с универсальным шаблоном указан конкретный тип ([System.Int32]), а обычный список остается обобщенным. Так как среда выполнения знает, что `List<int>` с универсальным шаблоном имеет тип <xref:System.Int32>, она может применить целочисленный массив для хранения элементов списка в памяти. В то же время для `ArrayList` без универсального списка нужно приводить все элементы к объекту. Как вы видите этом примере, дополнительные приведения занимают время и замедляют сортировку списка.

Еще одно преимущество понимания типа универсального шаблона заключается в упрощении отладки. При отладке универсального шаблона в C# вы заранее знаете тип каждого элемента в структуре данных. Без универсальных шаблонов вы бы не имели об этом никакого понятия.

## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C# — универсальные шаблоны](../../docs/csharp/programming-guide/generics/index.md)
