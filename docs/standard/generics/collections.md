---
title: Универсальные коллекции в .NET
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET], collections
- generic collections [.NET]
- generic types [.NET]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21d8ef3abfd16e11c9251edfc4f39b02e93eaab5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740925"
---
# <a name="generic-collections-in-net"></a><span data-ttu-id="6a0e4-102">Универсальные коллекции в .NET</span><span class="sxs-lookup"><span data-stu-id="6a0e4-102">Generic collections in .NET</span></span>

 <span data-ttu-id="6a0e4-103">Библиотека классов .NET предоставляет ряд универсальных классов коллекций в пространствах имен <xref:System.Collections.Generic> и <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-103">The .NET class library provides a number of generic collection classes in the <xref:System.Collections.Generic> and <xref:System.Collections.ObjectModel> namespaces.</span></span> <span data-ttu-id="6a0e4-104">См. дополнительные сведения о [часто используемых типах коллекций](../../../docs/standard/collections/commonly-used-collection-types.md).</span><span class="sxs-lookup"><span data-stu-id="6a0e4-104">For more detailed information about these classes, see [Commonly Used Collection Types](../../../docs/standard/collections/commonly-used-collection-types.md).</span></span>  
  
## <a name="systemcollectionsgeneric"></a><span data-ttu-id="6a0e4-105">System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="6a0e4-105">System.Collections.Generic</span></span>

 <span data-ttu-id="6a0e4-106">Многие универсальные типы коллекций являются прямыми аналогами неуниверсальных типов.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-106">Many of the generic collection types are direct analogs of nongeneric types.</span></span> <span data-ttu-id="6a0e4-107">Интерфейс <xref:System.Collections.Generic.Dictionary%602> — это универсальная версия <xref:System.Collections.Hashtable>; он использует для перечисления универсальную структуру <xref:System.Collections.Generic.KeyValuePair%602> вместо <xref:System.Collections.DictionaryEntry>.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-107"><xref:System.Collections.Generic.Dictionary%602> is a generic version of <xref:System.Collections.Hashtable>; it uses the generic structure <xref:System.Collections.Generic.KeyValuePair%602> for enumeration instead of <xref:System.Collections.DictionaryEntry>.</span></span>  
  
 <span data-ttu-id="6a0e4-108"><xref:System.Collections.Generic.List%601> — это универсальная версия <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-108"><xref:System.Collections.Generic.List%601> is a generic version of <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="6a0e4-109">Имеются универсальные классы <xref:System.Collections.Generic.Queue%601> и <xref:System.Collections.Generic.Stack%601>, соответствующие неуниверсальным версиям.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-109">There are generic <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601> classes that correspond to the nongeneric versions.</span></span>  
  
 <span data-ttu-id="6a0e4-110">Существуют универсальные и неуниверсальные версии <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-110">There are generic and nongeneric versions of <xref:System.Collections.Generic.SortedList%602>.</span></span> <span data-ttu-id="6a0e4-111">Обе эти версии являются гибридами словаря и списка.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-111">Both versions are hybrids of a dictionary and a list.</span></span> <span data-ttu-id="6a0e4-112">Универсальный класс <xref:System.Collections.Generic.SortedDictionary%602> представляет собой обычный словарь и не имеет неуниверсального аналога.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-112">The <xref:System.Collections.Generic.SortedDictionary%602> generic class is a pure dictionary and has no nongeneric counterpart.</span></span>  
  
 <span data-ttu-id="6a0e4-113">Универсальный класс <xref:System.Collections.Generic.LinkedList%601> является истинным связанным списком.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-113">The <xref:System.Collections.Generic.LinkedList%601> generic class is a true linked list.</span></span> <span data-ttu-id="6a0e4-114">У него нет неуниверсального аналога.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-114">It has no nongeneric counterpart.</span></span>  
  
## <a name="systemcollectionsobjectmodel"></a><span data-ttu-id="6a0e4-115">System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="6a0e4-115">System.Collections.ObjectModel</span></span>

 <span data-ttu-id="6a0e4-116">Универсальный класс <xref:System.Collections.ObjectModel.Collection%601> предоставляет базовый класс для создания собственных производных универсальных типов коллекций.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-116">The <xref:System.Collections.ObjectModel.Collection%601> generic class provides a base class for deriving your own generic collection types.</span></span> <span data-ttu-id="6a0e4-117">Класс <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> позволяет легко создавать доступные только для чтения коллекции на основе любого типа, реализующего универсальный интерфейс <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-117">The <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class provides an easy way to produce a read-only collection from any type that implements the <xref:System.Collections.Generic.IList%601> generic interface.</span></span> <span data-ttu-id="6a0e4-118">Универсальный класс <xref:System.Collections.ObjectModel.KeyedCollection%602> предоставляет способ хранения объектов, содержащих свои собственные ключи.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-118">The <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class provides a way to store objects that contain their own keys.</span></span>  
  
## <a name="other-generic-types"></a><span data-ttu-id="6a0e4-119">Прочие универсальные типы</span><span class="sxs-lookup"><span data-stu-id="6a0e4-119">Other generic types</span></span>

 <span data-ttu-id="6a0e4-120">Универсальная структура <xref:System.Nullable%601> позволяет использовать типы значений так, как будто им могут быть присвоены значения `null`.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-120">The <xref:System.Nullable%601> generic structure allows you to use value types as if they could be assigned `null`.</span></span> <span data-ttu-id="6a0e4-121">Это может быть полезно при работе с запросами к базе данных, где поля, содержащие типы значений, могут опускаться.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-121">This can be useful when working with database queries, where fields that contain value types can be missing.</span></span> <span data-ttu-id="6a0e4-122">Параметр универсального типа может принимать значения любого типа.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-122">The generic type parameter can be any value type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a0e4-123">В C# и Visual Basic нет необходимости явно использовать <xref:System.Nullable%601>, так как язык имеет синтаксис для типов, допускающий значение null.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-123">In C# and Visual Basic, it is not necessary to use <xref:System.Nullable%601> explicitly because the language has syntax for nullable types.</span></span> <span data-ttu-id="6a0e4-124">См. статьи о типах значений, допускающих значение NULL, [для C#](../../csharp/language-reference/builtin-types/nullable-value-types.md) и [Visual Basic](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="6a0e4-124">See [Nullable value types (C# reference)](../../csharp/language-reference/builtin-types/nullable-value-types.md) and [Nullable value types (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>
  
 <span data-ttu-id="6a0e4-125">Универсальная структура <xref:System.ArraySegment%601> предоставляет способ выделения диапазона элементов в одномерном массиве любого типа, начинающемся с нуля.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-125">The <xref:System.ArraySegment%601> generic structure provides a way to delimit a range of elements within a one-dimensional, zero-based array of any type.</span></span> <span data-ttu-id="6a0e4-126">Параметр универсального типа является типом элементов массива.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-126">The generic type parameter is the type of the array's elements.</span></span>  
  
 <span data-ttu-id="6a0e4-127">Универсальный делегат <xref:System.EventHandler%601> избавляет от необходимости объявления типа делегата для обработки событий, если такое событие соответствует шаблону обработки событий, используемому .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-127">The <xref:System.EventHandler%601> generic delegate eliminates the need to declare a delegate type to handle events, if your event follows the event-handling pattern used by the .NET Framework.</span></span> <span data-ttu-id="6a0e4-128">Предположим, что вы создали класс `MyEventArgs`, производный от <xref:System.EventArgs>, для хранения данных события.</span><span class="sxs-lookup"><span data-stu-id="6a0e4-128">For example, suppose you have created a `MyEventArgs` class, derived from <xref:System.EventArgs>, to hold the data for your event.</span></span> <span data-ttu-id="6a0e4-129">Затем вы можете объявить событие следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6a0e4-129">You can then declare the event as follows:</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="6a0e4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="6a0e4-130">See also</span></span>

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [<span data-ttu-id="6a0e4-131">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="6a0e4-131">Generics</span></span>](../../../docs/standard/generics/index.md)
- [<span data-ttu-id="6a0e4-132">Универсальные методы-делегаты для управления массивами и списками</span><span class="sxs-lookup"><span data-stu-id="6a0e4-132">Generic Delegates for Manipulating Arrays and Lists</span></span>](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)
- [<span data-ttu-id="6a0e4-133">Универсальные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6a0e4-133">Generic Interfaces</span></span>](../../../docs/standard/generics/interfaces.md)
