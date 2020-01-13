---
title: Часто используемые типы коллекций
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- collections [.NET Framework], generic
- objects [.NET Framework], grouping in collections
- generics [.NET Framework], collections
- IList interface, grouping data in collections
- IDictionary interface, grouping data in collections
- grouping data in collections, generic collection types
- Collections classes
- generic collections
ms.assetid: f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55
ms.openlocfilehash: 1004a2f9a0594d9150d147dec1e16b56205e0d13
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711406"
---
# <a name="commonly-used-collection-types"></a>Часто используемые типы коллекций
Типы коллекций — это распространенные виды коллекций данных, такие как хэш-таблицы, очереди, стеки, контейнеры, словари и списки.  
  
 Коллекции основаны на интерфейсе <xref:System.Collections.ICollection>, интерфейсе <xref:System.Collections.IList>, интерфейсе <xref:System.Collections.IDictionary> или их универсальных аналогах. Интерфейс <xref:System.Collections.IList> и <xref:System.Collections.IDictionary> являются производными от интерфейса <xref:System.Collections.ICollection>. Таким образом, все коллекции прямо или косвенно основаны на интерфейсе <xref:System.Collections.ICollection>. В коллекциях, основанных на интерфейсе <xref:System.Collections.IList> (например, <xref:System.Array>, <xref:System.Collections.ArrayList> или <xref:System.Collections.Generic.List%601>) или напрямую на интерфейсе <xref:System.Collections.ICollection> (например, <xref:System.Collections.Queue>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Stack>, <xref:System.Collections.Concurrent.ConcurrentStack%601> или <xref:System.Collections.Generic.LinkedList%601>), каждый элемент содержит только значение. В коллекциях, основанных на интерфейсе <xref:System.Collections.IDictionary> (например, классы <xref:System.Collections.Hashtable> и <xref:System.Collections.SortedList> и универсальные классы <xref:System.Collections.Generic.Dictionary%602> или <xref:System.Collections.Generic.SortedList%602>), или классах <xref:System.Collections.Concurrent.ConcurrentDictionary%602> каждый элемент содержит ключ и значение.  Класс <xref:System.Collections.ObjectModel.KeyedCollection%602> является уникальным, поскольку он представляет собой список значений с встроенными в значения ключами. Поэтому он функционирует как список и как словарь.  
  
 Универсальные коллекции являются наилучшим решением для реализации строгой типизации. Однако если язык не поддерживает универсальные шаблоны, пространство имен <xref:System.Collections> содержит базовые коллекции, такие как <xref:System.Collections.CollectionBase>, <xref:System.Collections.ReadOnlyCollectionBase> и <xref:System.Collections.DictionaryBase>, которые являются абстрактными базовыми классами с возможностью расширения для создания классов коллекций, которые являются строго типизированными. Если требуется эффективный доступ к многопотоковой коллекции, в пространстве имен <xref:System.Collections.Concurrent> следует использовать универсальные коллекции.  
  
 Коллекции могут различаться в зависимости от способов хранения и сортировки элементов, вариантов выполнения поисков и проведения сравнений. Класс <xref:System.Collections.Queue> и универсальный класс <xref:System.Collections.Generic.Queue%601> предоставляют списки по принципу "первым поступил — первым обслужен", а класс <xref:System.Collections.Stack> и универсальный класс <xref:System.Collections.Generic.Stack%601> предоставляют списки по принципу "последним поступил — первым обслужен". Класс <xref:System.Collections.SortedList> и универсальный класс <xref:System.Collections.Generic.SortedList%602> предоставляют сортируемые версии класса <xref:System.Collections.Hashtable> и универсального класса <xref:System.Collections.Generic.Dictionary%602>. Элементы <xref:System.Collections.Hashtable> или <xref:System.Collections.Generic.Dictionary%602> имеют доступ только по ключу элемента, а элементы <xref:System.Collections.SortedList> или <xref:System.Collections.ObjectModel.KeyedCollection%602> доступны с помощью ключа или индекса элемента. Индексы во всех коллекциях отсчитываются от нуля за исключением <xref:System.Array>, допускающего массивы с индексацией не от нуля.  
  
 Функция LINQ to Objects позволяет использовать запросы LINQ для доступа к объектам в памяти при условии, что тип объекта реализует интерфейс <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601>. LINQ запросы предоставляют общий шаблон для доступа к данным, являются более четкими и удобочитаемыми, чем стандартные циклы `foreach` , а также предоставляют возможности фильтрации, сортировки и группировки. LINQ запросы также могут повысить производительность. Дополнительные сведения см. в разделах [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) и [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Коллекции и структуры данных](../../../docs/standard/collections/index.md)|Описание различных типов коллекций, доступных в .NET Framework, в том числе стеков, очередей, списков, массивов и библиотек.|  
|[Типы коллекций Hashtable и Dictionary](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|Описание возможностей универсальных и неуниверсальных типов словарей на основе хэша.|  
|[Отсортированные типы коллекций](../../../docs/standard/collections/sorted-collection-types.md)|Описание классов, которые предоставляют функции сортировки списков и наборов.|  
|[Универсальные шаблоны](../../../docs/standard/generics/index.md)|Описание возможности универсальных шаблонов, в том числе универсальных коллекций, делегатов и интерфейсов, предоставляемых платформой .NET Framework. Ссылки на документацию по C#, Visual Basic и Visual C++, а также на вспомогательные технологии, такие как Reflection.|  
  
## <a name="reference"></a>Справочник  
 <xref:System.Collections?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
  
 <xref:System.Collections.ICollection?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.ICollection%601?displayProperty=nameWithType>  
  
 <xref:System.Collections.IList?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.IList%601?displayProperty=nameWithType>  
  
 <xref:System.Collections.IDictionary?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
