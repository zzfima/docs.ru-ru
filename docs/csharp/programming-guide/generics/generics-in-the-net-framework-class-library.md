---
title: "Универсальные шаблоны в библиотеке классов платформы .NET Framework (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], in .NET Framework class library
ms.assetid: afdd5477-6770-4686-8297-f58a4d749daf
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f3d5f15c92031301b68c6a702cf8d6b135cca36d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generics-in-the-net-framework-class-library-c-programming-guide"></a><span data-ttu-id="fac97-102">Универсальные шаблоны в библиотеке классов платформы .NET Framework (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="fac97-102">Generics in the .NET Framework Class Library (C# Programming Guide)</span></span>
<span data-ttu-id="fac97-103">Библиотека классов в платформе .NET Framework версии 2.0 предоставляет новое пространство имен <xref:System.Collections.Generic>, которое содержит несколько готовых к использованию универсальных классов коллекций и связанных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="fac97-103">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which includes several ready-to-use generic collection classes and associated interfaces.</span></span> <span data-ttu-id="fac97-104">Другие пространства имен, такие как <xref:System>, также предоставляют новые универсальные интерфейсы, например <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="fac97-104">Other namespaces, such as <xref:System>, also provide new generic interfaces such as <xref:System.IComparable%601>.</span></span> <span data-ttu-id="fac97-105">Эти классы и интерфейсы более эффективны и строго типизированы, чем неуниверсальные классы коллекций в более ранних выпусках платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fac97-105">These classes and interfaces are more efficient and type-safe than the non-generic collection classes provided in earlier releases of the .NET Framework.</span></span> <span data-ttu-id="fac97-106">Перед разработкой и реализацией собственных пользовательских классов коллекций нужно решить, будет ли класс использоваться либо наследоваться из одного из классов библиотеки классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fac97-106">Before designing and implementing your own custom collection classes, consider whether you can use or derive a class from one of the classes provided in the .NET Framework class library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac97-107">См. также</span><span class="sxs-lookup"><span data-stu-id="fac97-107">See Also</span></span>  
 <span data-ttu-id="fac97-108">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fac97-108">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fac97-109">[Когда следует использовать универсальные коллекции](../../../standard/collections/when-to-use-generic-collections.md) </span><span class="sxs-lookup"><span data-stu-id="fac97-109">[When to Use Generic Collections](../../../standard/collections/when-to-use-generic-collections.md) </span></span>  
 <span data-ttu-id="fac97-110">[Коллекции и структуры данных](../../../standard/collections/index.md) </span><span class="sxs-lookup"><span data-stu-id="fac97-110">[Collections and Data Structures](../../../standard/collections/index.md) </span></span>  
 [<span data-ttu-id="fac97-111">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="fac97-111">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)

