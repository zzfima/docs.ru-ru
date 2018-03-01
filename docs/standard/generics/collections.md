---
title: "Универсальные коллекции в .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], collections
- generic collections [.NET Framework]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7e7d11446c14cffbef1e5cade5f082874187636
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="generic-collections-in-the-net-framework"></a><span data-ttu-id="a9a68-102">Универсальные коллекции в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a9a68-102">Generic Collections in the .NET Framework</span></span>
<span data-ttu-id="a9a68-103">В этом разделе приводится обзор универсальных классов коллекций и других универсальных типов в составе платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9a68-103">This topic provides an overview of the generic collection classes and other generic types in the .NET Framework.</span></span>  
  
## <a name="generic-collections-in-the-net-framework"></a><span data-ttu-id="a9a68-104">Универсальные коллекции в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a9a68-104">Generic Collections in the .NET Framework</span></span>  
 <span data-ttu-id="a9a68-105">Библиотека классов .NET Framework предоставляет ряд универсальных классов коллекций в пространствах имен <xref:System.Collections.Generic> и <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="a9a68-105">The .NET Framework class library provides a number of generic collection classes in the <xref:System.Collections.Generic> and <xref:System.Collections.ObjectModel> namespaces.</span></span> <span data-ttu-id="a9a68-106">См. дополнительные сведения о [часто используемых типах коллекций](../../../docs/standard/collections/commonly-used-collection-types.md).</span><span class="sxs-lookup"><span data-stu-id="a9a68-106">For more information about these classes, see [Commonly Used Collection Types](../../../docs/standard/collections/commonly-used-collection-types.md).</span></span>  
  
### <a name="systemcollectionsgeneric"></a><span data-ttu-id="a9a68-107">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="a9a68-107">System.Collections.Generic</span></span>  
 <span data-ttu-id="a9a68-108">Многие универсальные типы коллекций являются прямыми аналогами неуниверсальных типов.</span><span class="sxs-lookup"><span data-stu-id="a9a68-108">Many of the generic collection types are direct analogs of nongeneric types.</span></span> <span data-ttu-id="a9a68-109">Интерфейс <xref:System.Collections.Generic.Dictionary%602> — это универсальная версия <xref:System.Collections.Hashtable>; он использует для перечисления универсальную структуру <xref:System.Collections.Generic.KeyValuePair%602> вместо <xref:System.Collections.DictionaryEntry>.</span><span class="sxs-lookup"><span data-stu-id="a9a68-109"><xref:System.Collections.Generic.Dictionary%602> is a generic version of <xref:System.Collections.Hashtable>; it uses the generic structure <xref:System.Collections.Generic.KeyValuePair%602> for enumeration instead of <xref:System.Collections.DictionaryEntry>.</span></span>  
  
 <span data-ttu-id="a9a68-110"><xref:System.Collections.Generic.List%601> — это универсальная версия <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="a9a68-110"><xref:System.Collections.Generic.List%601> is a generic version of <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="a9a68-111">Имеются универсальные классы <xref:System.Collections.Generic.Queue%601> и <xref:System.Collections.Generic.Stack%601>, соответствующие неуниверсальным версиям.</span><span class="sxs-lookup"><span data-stu-id="a9a68-111">There are generic <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601> classes that correspond to the nongeneric versions.</span></span>  
  
 <span data-ttu-id="a9a68-112">Существуют универсальные и неуниверсальные версии <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="a9a68-112">There are generic and nongeneric versions of <xref:System.Collections.Generic.SortedList%602>.</span></span> <span data-ttu-id="a9a68-113">Обе эти версии являются гибридами словаря и списка.</span><span class="sxs-lookup"><span data-stu-id="a9a68-113">Both versions are hybrids of a dictionary and a list.</span></span> <span data-ttu-id="a9a68-114">Универсальный класс <xref:System.Collections.Generic.SortedDictionary%602> представляет собой обычный словарь и не имеет неуниверсального аналога.</span><span class="sxs-lookup"><span data-stu-id="a9a68-114">The <xref:System.Collections.Generic.SortedDictionary%602> generic class is a pure dictionary and has no nongeneric counterpart.</span></span>  
  
 <span data-ttu-id="a9a68-115">Универсальный класс <xref:System.Collections.Generic.LinkedList%601> является истинным связанным списком.</span><span class="sxs-lookup"><span data-stu-id="a9a68-115">The <xref:System.Collections.Generic.LinkedList%601> generic class is a true linked list.</span></span> <span data-ttu-id="a9a68-116">У него нет неуниверсального аналога.</span><span class="sxs-lookup"><span data-stu-id="a9a68-116">It has no nongeneric counterpart.</span></span>  
  
### <a name="systemcollectionsobjectmodel"></a><span data-ttu-id="a9a68-117">System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="a9a68-117">System.Collections.ObjectModel</span></span>  
 <span data-ttu-id="a9a68-118">Универсальный класс <xref:System.Collections.ObjectModel.Collection%601> предоставляет базовый класс для создания собственных производных универсальных типов коллекций.</span><span class="sxs-lookup"><span data-stu-id="a9a68-118">The <xref:System.Collections.ObjectModel.Collection%601> generic class provides a base class for deriving your own generic collection types.</span></span> <span data-ttu-id="a9a68-119">Класс <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> позволяет легко создавать доступные только для чтения коллекции на основе любого типа, реализующего универсальный интерфейс <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="a9a68-119">The <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class provides an easy way to produce a read-only collection from any type that implements the <xref:System.Collections.Generic.IList%601> generic interface.</span></span> <span data-ttu-id="a9a68-120">Универсальный класс <xref:System.Collections.ObjectModel.KeyedCollection%602> предоставляет способ хранения объектов, содержащих свои собственные ключи.</span><span class="sxs-lookup"><span data-stu-id="a9a68-120">The <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class provides a way to store objects that contain their own keys.</span></span>  
  
## <a name="other-generic-types"></a><span data-ttu-id="a9a68-121">Прочие универсальные типы</span><span class="sxs-lookup"><span data-stu-id="a9a68-121">Other Generic Types</span></span>  
 <span data-ttu-id="a9a68-122">Универсальная структура <xref:System.Nullable%601> позволяет использовать типы значений так, как будто им могут быть присвоены значения `null`.</span><span class="sxs-lookup"><span data-stu-id="a9a68-122">The <xref:System.Nullable%601> generic structure allows you to use value types as if they could be assigned `null`.</span></span> <span data-ttu-id="a9a68-123">Это может быть полезно при работе с запросами к базе данных, где поля, содержащие типы значений, могут опускаться.</span><span class="sxs-lookup"><span data-stu-id="a9a68-123">This can be useful when working with database queries, where fields that contain value types can be missing.</span></span> <span data-ttu-id="a9a68-124">Параметр универсального типа может принимать значения любого типа.</span><span class="sxs-lookup"><span data-stu-id="a9a68-124">The generic type parameter can be any value type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9a68-125">В C# нет необходимости явно использовать <xref:System.Nullable%601>, так как язык имеет синтаксис для типов, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a9a68-125">In C# it is not necessary to use <xref:System.Nullable%601> explicitly because the language has syntax for nullable types.</span></span>  
  
 <span data-ttu-id="a9a68-126">Универсальная структура <xref:System.ArraySegment%601> предоставляет способ выделения диапазона элементов в одномерном массиве любого типа, начинающемся с нуля.</span><span class="sxs-lookup"><span data-stu-id="a9a68-126">The <xref:System.ArraySegment%601> generic structure provides a way to delimit a range of elements within a one-dimensional, zero-based array of any type.</span></span> <span data-ttu-id="a9a68-127">Параметр универсального типа является типом элементов массива.</span><span class="sxs-lookup"><span data-stu-id="a9a68-127">The generic type parameter is the type of the array's elements.</span></span>  
  
 <span data-ttu-id="a9a68-128">Универсальный делегат <xref:System.EventHandler%601> избавляет от необходимости объявления типа делегата для обработки событий, если такое событие соответствует шаблону обработки событий, используемому [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9a68-128">The <xref:System.EventHandler%601> generic delegate eliminates the need to declare a delegate type to handle events, if your event follows the event-handling pattern used by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="a9a68-129">Предположим, что вы создали класс `MyEventArgs`, производный от <xref:System.EventArgs>, для хранения данных события.</span><span class="sxs-lookup"><span data-stu-id="a9a68-129">For example, suppose you have created a `MyEventArgs` class, derived from <xref:System.EventArgs>, to hold the data for your event.</span></span> <span data-ttu-id="a9a68-130">Затем вы можете объявить событие следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a9a68-130">You can then declare the event as follows:</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="a9a68-131">См. также</span><span class="sxs-lookup"><span data-stu-id="a9a68-131">See Also</span></span>  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
 <xref:System.Collections.ObjectModel?displayProperty=nameWithType>  
 [<span data-ttu-id="a9a68-132">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="a9a68-132">Generics</span></span>](../../../docs/standard/generics/index.md)  
 [<span data-ttu-id="a9a68-133">Универсальные методы-делегаты для управления массивами и списками</span><span class="sxs-lookup"><span data-stu-id="a9a68-133">Generic Delegates for Manipulating Arrays and Lists</span></span>](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)  
 [<span data-ttu-id="a9a68-134">Универсальные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a9a68-134">Generic Interfaces</span></span>](../../../docs/standard/generics/interfaces.md)
