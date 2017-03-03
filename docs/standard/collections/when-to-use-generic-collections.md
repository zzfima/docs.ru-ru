---
title: "Когда следует использовать универсальные коллекции"
description: "Когда следует использовать универсальные коллекции"
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 971e08bd-b63f-4832-9e61-9f65cbedd352
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: bde317c165981775330e1d0d8261d355e2401bc9
ms.lasthandoff: 03/03/2017

---

# <a name="when-to-use-generic-collections"></a>Когда следует использовать универсальные коллекции

Использование универсальных коллекций является рекомендуемой практикой, поскольку при этом сразу же обеспечивается безопасность типов без необходимости наследования от базового типа коллекции и реализации элементов определенного типа. Типы универсальных коллекций обычно работают лучше, чем соответствующие типы неуниверсальных коллекций (и лучше, чем типы, являющиеся производными от базовых типов неуниверсальных коллекций), если элементами коллекции являются типы значений, поскольку при использовании универсальных коллекций упаковывать элементы не требуется. 

Универсальные классы-коллекции в пространстве имен [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) следует использовать в случаях, когда несколько потоков могут одновременно добавлять элементы в коллекцию или удалять их оттуда.

Следующие универсальные типы соответствуют существующим типам коллекций. 

*   [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) — это универсальный класс, соответствующий [ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList).

*   [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) и [ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) — это универсальные классы, соответствующие [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable). 

*   [Collection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.Collection-1) — это универсальный класс, соответствующий [CollectionBase](https://docs.microsoft.com/dotnet/core/api/System.Collections.CollectionBase). `Collection<T>` может использоваться как базовый класс, но в отличие от `CollectionBase` он не является абстрактным. Это значительно упрощает его использование.

*   [ReadOnlyCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.ReadOnlyCollection-1) — это универсальный класс, соответствующий [ReadOnlyCollectionBase](https://docs.microsoft.com/dotnet/core/api/System.Collections.ReadOnlyCollectionBase). `ReadOnlyCollection<T>` не является абстрактным и имеет конструктор, упрощающий представление существующего класса [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) в виде коллекции только для чтения.

*   Универсальные классы [Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1), [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1), [Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1), [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) и [SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) соответствуют аналогичным неуниверсальным классам с теми же именами.

## <a name="additional-types"></a>Дополнительные типы

Несколько типов универсальных коллекций не имеют неуниверсальных аналогов. В их число входят следующие. 

*   [LinkedList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1) является связанным списком общего назначения, обеспечивающий выполнение операций вставки и удаления O(1).

*   [SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) — это сортируемый словарь с операциями вставки и извлечения O(log n), что делает его полезной альтернативой для [SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2). 

*   [KeyedCollection&lt;TKey, TItem&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) — это гибрид списка и словаря, который предоставляет способ хранения объектов, содержащих свои собственные ключи.

*   [BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) реализует класс коллекции с функциями границы и блокировки.

*   [ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) предоставляет возможности быстрой вставки и удаления неупорядоченных элементов.

## <a name="linq-to-objects"></a>LINQ to Objects

Функция LINQ to Objects позволяет использовать запросы LINQ для доступа к объектам в памяти при условии, что тип объекта реализует интерфейс [System.Collections.IEnumerable](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable) или [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1). LINQ запросы предоставляют общий шаблон для доступа к данным, являются более четкими и удобочитаемыми, чем стандартные циклы `foreach`, а также предоставляют возможности фильтрации, сортировки и группировки. LINQ запросы также могут повысить производительность.

## <a name="additional-functionality"></a>Дополнительные функциональные возможности

Некоторые универсальные типы имеют функциональные возможности, отсутствующие в неуниверсальных коллекциях. Например, класс [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1), который соответствует неуниверсальному классу [ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList), имеет ряд методов, которые принимают универсальные делегаты, такие как делегат [Predicate&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Predicate-1), который позволяет указать методы для поиска в списке, делегат [Action&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Action-1), который представляет методы, выполняемые с каждым элементом списка.

Класс [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) позволяет задавать свои собственные реализации универсального интерфейса [IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1) для сортировки и поиска в списке. Эта возможность также имеется в классах [SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) и [SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2). Кроме того эти классы позволяют задавать функции сравнения при создании коллекции. Точно так же классы [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) и [KeyedCollection&lt;TKey, TItem&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) позволяют задавать собственные компараторы равенства.

## <a name="see-also"></a>См. также

[Коллекции и структуры данных](index.md) 

[Часто используемые типы коллекций](commonly-used-collection-types.md)

