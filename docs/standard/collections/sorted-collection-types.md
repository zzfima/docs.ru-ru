---
title: "Отсортированные типы коллекций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SortedDictionary collection type
- SortedList class, grouping data in collections
- grouping data in collections, SortedList collection type
- SortedList collection type
- collections [.NET Framework], SortedList collection type
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7efe53d472e1789d49acc3973acdf190c8ff6662
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="sorted-collection-types"></a><span data-ttu-id="3a69c-102">Отсортированные типы коллекций</span><span class="sxs-lookup"><span data-stu-id="3a69c-102">Sorted Collection Types</span></span>
<span data-ttu-id="3a69c-103">Класс <xref:System.Collections.SortedList?displayProperty=nameWithType>, универсальный класс <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> и универсальный класс <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> похожи на класс <xref:System.Collections.Hashtable> и универсальный класс <xref:System.Collections.Generic.Dictionary%602> в том, что они реализуют интерфейс <xref:System.Collections.IDictionary>, но сортировка элементов в них осуществляется по ключу. Кроме того, в них отсутствует возможность вставки O(1) и извлечения характеристик хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="3a69c-103">The <xref:System.Collections.SortedList?displayProperty=nameWithType> class, the <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> generic class, and the <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> generic class are similar to the <xref:System.Collections.Hashtable> class and the <xref:System.Collections.Generic.Dictionary%602> generic class in that they implement the <xref:System.Collections.IDictionary> interface, but they maintain their elements in sort order by key, and they do not have the O(1) insertion and retrieval characteristic of hash tables.</span></span> <span data-ttu-id="3a69c-104">Эти три класса имеют ряд схожих свойств:</span><span class="sxs-lookup"><span data-stu-id="3a69c-104">The three classes have several features in common:</span></span>  
  
-   <span data-ttu-id="3a69c-105">Все три класса реализуют интерфейс <xref:System.Collections.IDictionary?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-105">All three classes implement the <xref:System.Collections.IDictionary?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="3a69c-106">Два универсальных класса также реализуют универсальный интерфейс <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-106">The two generic classes also implement the <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType> generic interface.</span></span>  
  
-   <span data-ttu-id="3a69c-107">Каждый элемент является парой ключ-значение для перечисления.</span><span class="sxs-lookup"><span data-stu-id="3a69c-107">Each element is a key/value pair for enumeration purposes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a69c-108">Неуниверсальный класс <xref:System.Collections.SortedList> возвращает при перечислении объекты <xref:System.Collections.DictionaryEntry>, несмотря на то, что два универсальных типа возвращают объекты <xref:System.Collections.Generic.KeyValuePair%602>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-108">The nongeneric <xref:System.Collections.SortedList> class returns <xref:System.Collections.DictionaryEntry> objects when enumerated, although the two generic types return <xref:System.Collections.Generic.KeyValuePair%602> objects.</span></span>  
  
-   <span data-ttu-id="3a69c-109">Элементы сортируются в соответствии с реализацией <xref:System.Collections.IComparer?displayProperty=nameWithType> (для неуниверсального класса <xref:System.Collections.SortedList>) или с реализацией <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> (для двух универсальных классов).</span><span class="sxs-lookup"><span data-stu-id="3a69c-109">Elements are sorted according to a <xref:System.Collections.IComparer?displayProperty=nameWithType> implementation (for nongeneric <xref:System.Collections.SortedList>) or a <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> implementation (for the two generic classes).</span></span>  
  
-   <span data-ttu-id="3a69c-110">Каждый класс предоставляет свойства, которые возвращают коллекции, содержащие только ключи или только значения.</span><span class="sxs-lookup"><span data-stu-id="3a69c-110">Each class provides properties that return collections containing only the keys or only the values.</span></span>  
  
 <span data-ttu-id="3a69c-111">В таблице ниже перечислены некоторые отличия между двумя классами отсортированных списков и классом <xref:System.Collections.Generic.SortedDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-111">The following table lists some of the differences between the two sorted list classes and the <xref:System.Collections.Generic.SortedDictionary%602> class.</span></span>  
  
|<span data-ttu-id="3a69c-112">Неуниверсальный класс <xref:System.Collections.SortedList> и универсальный класс <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-112"><xref:System.Collections.SortedList> nongeneric class and <xref:System.Collections.Generic.SortedList%602> generic class</span></span>|<span data-ttu-id="3a69c-113">Универсальный класс <xref:System.Collections.Generic.SortedDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-113"><xref:System.Collections.Generic.SortedDictionary%602> generic class</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="3a69c-114">Свойства, возвращающие ключи и значения, индексируются, что позволяет выполнять эффективное индексированное извлечение.</span><span class="sxs-lookup"><span data-stu-id="3a69c-114">The properties that return keys and values are indexed, allowing efficient indexed retrieval.</span></span>|<span data-ttu-id="3a69c-115">Неиндексированное извлечение.</span><span class="sxs-lookup"><span data-stu-id="3a69c-115">No indexed retrieval.</span></span>|  
|<span data-ttu-id="3a69c-116">Извлечение — O(log `n`).</span><span class="sxs-lookup"><span data-stu-id="3a69c-116">Retrieval is O(log `n`).</span></span>|<span data-ttu-id="3a69c-117">Извлечение — O(log `n`).</span><span class="sxs-lookup"><span data-stu-id="3a69c-117">Retrieval is O(log `n`).</span></span>|  
|<span data-ttu-id="3a69c-118">Вставка и удаление, как правило, являются O(`n`), но вставка является O(log `n`) для данных, которые уже отсортированы, чтобы каждый элемент добавлялся в конец списка.</span><span class="sxs-lookup"><span data-stu-id="3a69c-118">Insertion and removal are generally O(`n`); however, insertion is O(log `n`) for data that are already in sort order, so that each element is added to the end of the list.</span></span> <span data-ttu-id="3a69c-119">(Предполагается, что изменение размера не требуется.)</span><span class="sxs-lookup"><span data-stu-id="3a69c-119">(This assumes that a resize is not required.)</span></span>|<span data-ttu-id="3a69c-120">Вставка и удаление являются O(log `n`).</span><span class="sxs-lookup"><span data-stu-id="3a69c-120">Insertion and removal are O(log `n`).</span></span>|  
|<span data-ttu-id="3a69c-121">Использует меньше памяти, чем <xref:System.Collections.Generic.SortedDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-121">Uses less memory than a <xref:System.Collections.Generic.SortedDictionary%602>.</span></span>|<span data-ttu-id="3a69c-122">Использует больше памяти, чем неуниверсальный класс <xref:System.Collections.SortedList> и универсальный класс <xref:System.Collections.Generic.SortedList%602>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-122">Uses more memory than the <xref:System.Collections.SortedList> nongeneric class and the <xref:System.Collections.Generic.SortedList%602> generic class.</span></span>|  
  
 <span data-ttu-id="3a69c-123">Для отсортированных списков или словарей, которые должны быть доступны одновременно из множества потоков, вы можете добавить в производный класс от <xref:System.Collections.Concurrent.ConcurrentDictionary%602> логику сортировки.</span><span class="sxs-lookup"><span data-stu-id="3a69c-123">For sorted lists or dictionaries that must be accessible concurrently from multiple threads, you can add sorting logic to a class that derives from <xref:System.Collections.Concurrent.ConcurrentDictionary%602>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a69c-124">Для значений, содержащих собственные ключи (например, записи о сотрудниках, содержащие идентификационный номер сотрудника), вы можете создать коллекцию с ключами, имеющую некоторые характеристики списка и некоторые характеристики словаря. Для этого необходимо создать производный класс от универсального класса <xref:System.Collections.ObjectModel.KeyedCollection%602>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-124">For values that contain their own keys (for example, employee records that contain an employee ID number), you can create a keyed collection that has some characteristics of a list and some characteristics of a dictionary by deriving from the <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class.</span></span>  
  
 <span data-ttu-id="3a69c-125">Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], класс <xref:System.Collections.Generic.SortedSet%601> предоставляет самобалансируемое дерево, в котором после операций вставки, удаления или поиска данные сохраняются в отсортированном порядке.</span><span class="sxs-lookup"><span data-stu-id="3a69c-125">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the <xref:System.Collections.Generic.SortedSet%601> class provides a self-balancing tree that maintains data in sorted order after insertions, deletions, and searches.</span></span> <span data-ttu-id="3a69c-126">Этот класс и класс <xref:System.Collections.Generic.HashSet%601> реализуют интерфейс <xref:System.Collections.Generic.ISet%601>.</span><span class="sxs-lookup"><span data-stu-id="3a69c-126">This class and the <xref:System.Collections.Generic.HashSet%601> class implement the <xref:System.Collections.Generic.ISet%601> interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a69c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3a69c-127">See Also</span></span>  
 <xref:System.Collections.IDictionary?displayProperty=nameWithType>  
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>  
 [<span data-ttu-id="3a69c-128">Часто используемые типы коллекций</span><span class="sxs-lookup"><span data-stu-id="3a69c-128">Commonly Used Collection Types</span></span>](../../../docs/standard/collections/commonly-used-collection-types.md)
