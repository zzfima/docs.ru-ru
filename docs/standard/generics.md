---
title: "Обзор универсальных типов (универсальных шаблонов)"
description: "Сведения о том, как универсальные шаблоны действуют в качестве шаблона кода, позволяющего разработчикам определять типобезопасные структуры данных, не выполняя реальный тип данных."
keywords: .NET, .NET Core
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
ms.openlocfilehash: 08b8de2fe17a0032a1c1180667f39b1d6ce0feb6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="generic-types-generics-overview"></a><span data-ttu-id="1d3b4-104">Обзор универсальных типов (универсальных шаблонов)</span><span class="sxs-lookup"><span data-stu-id="1d3b4-104">Generic Types (Generics) Overview</span></span>

<span data-ttu-id="1d3b4-105">В C# мы постоянно используем универсальные шаблоны — как явно, так и неявно.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-105">We use generics all the time in C#, whether implicitly or explicitly.</span></span> <span data-ttu-id="1d3b4-106">Замечали ли вы, что работаете с IEnumerable<T> при использовании LINQ в C#?</span><span class="sxs-lookup"><span data-stu-id="1d3b4-106">When you use LINQ in C#, did you ever notice that you are working with IEnumerable<T>?</span></span> <span data-ttu-id="1d3b4-107">Или, может быть, вы замечали, что большинство методов возвращает IQueryable<T> в примере "универсального репозитория" для обращения к базам данных через Entity Framework?</span><span class="sxs-lookup"><span data-stu-id="1d3b4-107">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable<T>?</span></span> <span data-ttu-id="1d3b4-108">Возможно, вы задавались вопросом, что такое **T** в этих примерах и зачем это нужно?</span><span class="sxs-lookup"><span data-stu-id="1d3b4-108">You may have wondered what the **T** is in these examples and why is it in there?</span></span>

<span data-ttu-id="1d3b4-109">Универсальные шаблоны, впервые появившиеся в .NET Framework 2.0, вносили изменения как для языка C#, так и для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-109">First introduced to the .NET Framework 2.0, generics involved changes to both the C# language and the Common Language Runtime (CLR).</span></span> <span data-ttu-id="1d3b4-110">**Универсальные шаблоны** представляют собой "шаблон кода", позволяющий разработчикам определять [типобезопасные](https://msdn.microsoft.com/library/hbzz1a9a.aspx) структуры данных, не выполняя реальный тип данных.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-110">**Generics** are essentially a "code template" that allows developers to define [type-safe](https://msdn.microsoft.com/library/hbzz1a9a.aspx) data structures without committing to an actual data type.</span></span> <span data-ttu-id="1d3b4-111">Например, `List<T>` — это [универсальная коллекция](xref:System.Collections.Generic), которую можно объявить и использовать с любым типом: `List<int>`, `List<string>`, `List<Person>` и т. д.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-111">For example, `List<T>` is a [Generic Collection](xref:System.Collections.Generic) that can be declared and used with any type: `List<int>`, `List<string>`, `List<Person>`, etc.</span></span>

<span data-ttu-id="1d3b4-112">Так в чем же дело?</span><span class="sxs-lookup"><span data-stu-id="1d3b4-112">So, what’s the point?</span></span> <span data-ttu-id="1d3b4-113">Почему универсальные шаблоны так удобны?</span><span class="sxs-lookup"><span data-stu-id="1d3b4-113">Why are generics useful?</span></span> <span data-ttu-id="1d3b4-114">Чтобы понять это, нужно взглянуть на конкретный класс до и после добавления универсальных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-114">In order to understand this, we need to take a look at a specific class before and after adding generics.</span></span> <span data-ttu-id="1d3b4-115">Давайте рассмотрим `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-115">Let’s look at the `ArrayList`.</span></span> <span data-ttu-id="1d3b4-116">В C# 1.0 элементы `ArrayList` имели тип `object`.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-116">In C# 1.0, the `ArrayList` elements were of type `object`.</span></span> <span data-ttu-id="1d3b4-117">Это означало, что любой добавляемый элемент автоматически преобразовывался в `object`. То же самое происходит при чтении элементов из списка (этот процесс называется, соответственно, [упаковкой-](https://msdn.microsoft.com/library/yz2be5wk.aspx) и распаковкой-преобразованием).</span><span class="sxs-lookup"><span data-stu-id="1d3b4-117">This meant that any element that was added was silently converted into an `object`; same thing happens on reading the elements from the list (this process is known as [boxing](https://msdn.microsoft.com/library/yz2be5wk.aspx) and unboxing respectively).</span></span> <span data-ttu-id="1d3b4-118">Упаковка-преобразование и распаковка-преобразование снижают производительность.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-118">Boxing and unboxing have an impact of performance.</span></span> <span data-ttu-id="1d3b4-119">Кроме того, во время компиляции невозможно определить, какой именно тип имеют данные в списке.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-119">More than that, however, there is no way to tell at compile time what is the actual type of the data in the list.</span></span> <span data-ttu-id="1d3b4-120">Это приводит к созданию кода, который неудобно обслуживать.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-120">This makes for some fragile code.</span></span> <span data-ttu-id="1d3b4-121">Универсальные шаблоны решают эту проблему, предоставляя дополнительные сведения о типе данных, которые будет содержать каждый экземпляр в списке.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-121">Generics solve this problem by providing additional information the type of data each instance of list will contain.</span></span> <span data-ttu-id="1d3b4-122">Проще говоря, вы можете добавить только целые числа в `List<int>`, только людей в `List<Person>` и т. д.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-122">Put simply, you can only add integers to `List<int>` and only add Persons to `List<Person>`, etc.</span></span>

<span data-ttu-id="1d3b4-123">Универсальные шаблоны также доступны во время выполнения или **материализованы**.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-123">Generics are also available at runtime, or **reified**.</span></span> <span data-ttu-id="1d3b4-124">Это означает, что среда выполнения знает, какой тип структуры данных используется, и может хранить ее в памяти более эффективно.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-124">This means the runtime knows what type of data structure you are using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="1d3b4-125">Здесь приведена небольшая программа, иллюстрирующая пользу от сведений о типе структуры данных во время выполнения:</span><span class="sxs-lookup"><span data-stu-id="1d3b4-125">Here is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

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

<span data-ttu-id="1d3b4-126">Программа выдает следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="1d3b4-126">This program yields the following output:</span></span>

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms
```

<span data-ttu-id="1d3b4-127">Прежде всего, здесь видно, что сортировка этого универсального списка осуществляется значительно быстрее, чем неуниверсального.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-127">The first thing you notice here is that sorting the generic list is significantly faster than for the non-generic list.</span></span> <span data-ttu-id="1d3b4-128">Можно также заметить, что для универсального списка тип является конкретным ([System.Int32]), тогда как для неуниверсального списка — обобщенным.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-128">You might also notice that the type for the generic list is distinct ([System.Int32]) whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="1d3b4-129">Поскольку среда выполнения знает, что универсальный `List<int>` имеет тип int, она может сохранить элементы списка в базовом целочисленном массиве в памяти, в то время как неуниверсальному `ArrayList` приходится приводить все элементы списка в качестве объекта, сохраненного в массиве объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-129">Because the runtime knows the generic `List<int>` is of type int, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element as an object as stored in an object array in memory.</span></span> <span data-ttu-id="1d3b4-130">Как показано в этом примере, лишние приведения занимают время и замедляют сортировку списка.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-130">As shown through this example, the extra castings take up time and slow down the list sort.</span></span>

<span data-ttu-id="1d3b4-131">Последнее преимущество заключается в упрощении отладки.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-131">The last useful thing about the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="1d3b4-132">При отладке универсального шаблона в C# вы знаете тип каждого элемента в структуре данных.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-132">When you are debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="1d3b4-133">Без универсальных шаблонов вы бы не имели об этом никакого понятия.</span><span class="sxs-lookup"><span data-stu-id="1d3b4-133">Without generics, you would have no idea what type each element was.</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="1d3b4-134">Дополнительные сведения и ресурсы</span><span class="sxs-lookup"><span data-stu-id="1d3b4-134">Further reading and resources</span></span>

*   [<span data-ttu-id="1d3b4-135">Введение в универсальные шаблоны C#</span><span class="sxs-lookup"><span data-stu-id="1d3b4-135">An Introduction to C# Generics</span></span>](https://msdn.microsoft.com/library/ms379564.aspx)
*   [<span data-ttu-id="1d3b4-136">Руководство по программированию на C# — универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="1d3b4-136">C# Programming Guide - Generics</span></span>](https://msdn.microsoft.com/library/512aeb7t.aspx)
