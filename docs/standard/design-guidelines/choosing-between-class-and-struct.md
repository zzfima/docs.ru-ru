---
title: "Выбор между классом и структурой"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 68a3d2c7335ff15706925f9a7986164e6d9c0c36
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="choosing-between-class-and-struct"></a><span data-ttu-id="5c057-102">Выбор между классом и структурой</span><span class="sxs-lookup"><span data-stu-id="5c057-102">Choosing Between Class and Struct</span></span>
<span data-ttu-id="5c057-103">Одним из основных проектных решений сталкивается каждый конструктор framework является разработки тип как класс (ссылочный тип) или как структура (тип значения).</span><span class="sxs-lookup"><span data-stu-id="5c057-103">One of the basic design decisions every framework designer faces is whether to design a type as a class (a reference type) or as a struct (a value type).</span></span> <span data-ttu-id="5c057-104">При этом важно понять различия в поведении ссылочных типов и типов значений.</span><span class="sxs-lookup"><span data-stu-id="5c057-104">Good understanding of the differences in the behavior of reference types and value types is crucial in making this choice.</span></span>  
  
 <span data-ttu-id="5c057-105">Первый разница между ссылочные типы и типы значений, которые мы будет рассматривать в том, что ссылочные типы, выделенными в куче и сбора мусора, тогда как выделяются типы значений, либо в стеке или встроенные, содержащую типы и освобождается при стека Освобождает или когда возвращает освобожденные своим вмещающим типом.</span><span class="sxs-lookup"><span data-stu-id="5c057-105">The first difference between reference types and value types we will consider is that reference types are allocated on the heap and garbage-collected, whereas value types are allocated either on the stack or inline in containing types and deallocated when the stack unwinds or when their containing type gets deallocated.</span></span> <span data-ttu-id="5c057-106">Таким образом операций выделения и освобождения типов значений, в целом дешевле, чем операций выделения и освобождения ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="5c057-106">Therefore, allocations and deallocations of value types are in general cheaper than allocations and deallocations of reference types.</span></span>  
  
 <span data-ttu-id="5c057-107">Далее ссылочные типы массивов выделяются вне строки, то есть элементы массива только ссылки на экземпляры ссылочного типа, размещенных в куче.</span><span class="sxs-lookup"><span data-stu-id="5c057-107">Next, arrays of reference types are allocated out-of-line, meaning the array elements are just references to instances of the reference type residing on the heap.</span></span> <span data-ttu-id="5c057-108">Массивы типов значений выделяются встроенный, это означает, что элементы массива являются фактических экземпляров типа значения.</span><span class="sxs-lookup"><span data-stu-id="5c057-108">Value type arrays are allocated inline, meaning that the array elements are the actual instances of the value type.</span></span> <span data-ttu-id="5c057-109">Поэтому операций выделения и освобождения массивов типа значения являются значительно дешевле, чем операций выделения и освобождения массивов ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="5c057-109">Therefore, allocations and deallocations of value type arrays are much cheaper than allocations and deallocations of reference type arrays.</span></span> <span data-ttu-id="5c057-110">Кроме того в большинстве случаев массивы типов значений демонстрируют гораздо лучше расположение ссылок.</span><span class="sxs-lookup"><span data-stu-id="5c057-110">In addition, in a majority of cases value type arrays exhibit much better locality of reference.</span></span>  
  
 <span data-ttu-id="5c057-111">Следующее различие связана с памятью.</span><span class="sxs-lookup"><span data-stu-id="5c057-111">The next difference is related to memory usage.</span></span> <span data-ttu-id="5c057-112">Типы значений упаковываться когда приводится к типу ссылки или один из интерфейсов, которые они реализуют.</span><span class="sxs-lookup"><span data-stu-id="5c057-112">Value types get boxed when cast to a reference type or one of the interfaces they implement.</span></span> <span data-ttu-id="5c057-113">Они получают распакованный при приведения к типу значения.</span><span class="sxs-lookup"><span data-stu-id="5c057-113">They get unboxed when cast back to the value type.</span></span> <span data-ttu-id="5c057-114">Поскольку поля называются объекты, размещенных в куче сбора мусора, слишком сильно упаковка-преобразование и распаковка-преобразование может иметь отрицательное влияние на куче сборщика мусора и в конечном счете производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="5c057-114">Because boxes are objects that are allocated on the heap and are garbage-collected, too much boxing and unboxing can have a negative impact on the heap, the garbage collector, and ultimately the performance of the application.</span></span>  <span data-ttu-id="5c057-115">Напротив такие упаковка-преобразование не происходит, приводятся ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="5c057-115">In contrast, no such boxing occurs as reference types are cast.</span></span>  
  
 <span data-ttu-id="5c057-116">Назначение типа ссылок скопируйте справочник, в то время как назначение типа значение копирование всего значения.</span><span class="sxs-lookup"><span data-stu-id="5c057-116">Next, reference type assignments copy the reference, whereas value type assignments copy the entire value.</span></span> <span data-ttu-id="5c057-117">Таким образом назначения больших ссылочных типов дешевле, чем назначения типов больших значений.</span><span class="sxs-lookup"><span data-stu-id="5c057-117">Therefore, assignments of large reference types are cheaper than assignments of large value types.</span></span>  
  
 <span data-ttu-id="5c057-118">Наконец ссылочные типы передаются по ссылке, тогда как типы значений передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="5c057-118">Finally, reference types are passed by reference, whereas value types are passed by value.</span></span> <span data-ttu-id="5c057-119">Изменения в экземпляр ссылочного типа, влияют на все ссылки, указывающие на экземпляр.</span><span class="sxs-lookup"><span data-stu-id="5c057-119">Changes to an instance of a reference type affect all references pointing to the instance.</span></span> <span data-ttu-id="5c057-120">Экземпляры типов значения копируются в том случае, когда они передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="5c057-120">Value type instances are copied when they are passed by value.</span></span> <span data-ttu-id="5c057-121">При изменении экземпляра типа значения, она безусловно не влияет на все ее копии.</span><span class="sxs-lookup"><span data-stu-id="5c057-121">When an instance of a value type is changed, it of course does not affect any of its copies.</span></span> <span data-ttu-id="5c057-122">Поскольку копий не явно создан пользователем, но неявно создаются, если аргументы передаются или значения возвращаются, типы значений, которые могут быть изменены могут показаться сложными многим пользователям.</span><span class="sxs-lookup"><span data-stu-id="5c057-122">Because the copies are not created explicitly by the user but are implicitly created when arguments are passed or return values are returned, value types that can be changed can be confusing to many users.</span></span> <span data-ttu-id="5c057-123">Таким образом типы значений должны быть неизменными.</span><span class="sxs-lookup"><span data-stu-id="5c057-123">Therefore, value types should be immutable.</span></span>  
  
 <span data-ttu-id="5c057-124">Как правило большинство типов в платформе должно быть классы.</span><span class="sxs-lookup"><span data-stu-id="5c057-124">As a rule of thumb, the majority of types in a framework should be classes.</span></span> <span data-ttu-id="5c057-125">Однако, существуют некоторые ситуации, в которых характеристики типа значение сделать ее удобнее использовать структуры.</span><span class="sxs-lookup"><span data-stu-id="5c057-125">There are, however, some situations in which the characteristics of a value type make it more appropriate to use structs.</span></span>  
  
 <span data-ttu-id="5c057-126">**✓ Попробуйте** определение структуры вместо класса, если экземпляры типа невелики и имеют короткое время существования или внедрены в другие объекты.</span><span class="sxs-lookup"><span data-stu-id="5c057-126">**✓ CONSIDER** defining a struct instead of a class if instances of the type are small and commonly short-lived or are commonly embedded in other objects.</span></span>  
  
 <span data-ttu-id="5c057-127">**X ИЗБЕГАЙТЕ** определение структуры, если тип не содержит все следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="5c057-127">**X AVOID** defining a struct unless the type has all of the following characteristics:</span></span>  
  
-   <span data-ttu-id="5c057-128">Логически представляет одно значение, аналогично типы-примитивы (`int`, `double`и т. д.).</span><span class="sxs-lookup"><span data-stu-id="5c057-128">It logically represents a single value, similar to primitive types (`int`, `double`, etc.).</span></span>  
  
-   <span data-ttu-id="5c057-129">Она имеет размер экземпляра менее 16 байтов.</span><span class="sxs-lookup"><span data-stu-id="5c057-129">It has an instance size under 16 bytes.</span></span>  
  
-   <span data-ttu-id="5c057-130">Является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="5c057-130">It is immutable.</span></span>  
  
-   <span data-ttu-id="5c057-131">Должен быть упакован часто не будет.</span><span class="sxs-lookup"><span data-stu-id="5c057-131">It will not have to be boxed frequently.</span></span>  
  
 <span data-ttu-id="5c057-132">Во всех остальных случаях необходимо определить типы классов.</span><span class="sxs-lookup"><span data-stu-id="5c057-132">In all other cases, you should define your types as classes.</span></span>  
  
 <span data-ttu-id="5c057-133">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="5c057-133">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5c057-134">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="5c057-134">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c057-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5c057-135">See Also</span></span>  
 [<span data-ttu-id="5c057-136">Рекомендации по разработке типов</span><span class="sxs-lookup"><span data-stu-id="5c057-136">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="5c057-137">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="5c057-137">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
