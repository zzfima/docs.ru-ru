---
title: "Часто используемые типы коллекций"
description: "Часто используемые типы коллекций"
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 55861611-1e40-4cc2-9ec5-0b2df4ba6c0c
translationtype: Human Translation
ms.sourcegitcommit: d4e7ef84480aa9f735fb8d1ff03c9e8a61127c83
ms.openlocfilehash: 6cadcd91810f08900b58e402240e8a469fad2018

---

# <a name="commonly-used-collection-types"></a>Часто используемые типы коллекций

Типы коллекций — это распространенные виды коллекций данных, такие как хэш-таблицы, очереди, стеки, контейнеры, словари и списки.

Коллекции основаны на интерфейсе [`ICollection`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection), интерфейсе [`IList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IList), интерфейсе [`IDictionary`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary) или их универсальных аналогах. Интерфейс `IList` и `IDictionary` являются производными от интерфейса `ICollection`. Таким образом, все коллекции прямо или косвенно основаны на интерфейсе `ICollection`. В коллекциях, основанных на интерфейсе `IList` (например, [`Array`](https://docs.microsoft.com/dotnet/core/api/System.Array), [`ArrayList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList) или [`List<T>)`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1)) или напрямую на интерфейсе `ICollection` (например, [`Queue`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Queue), [`ConcurrentQueue<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1), [`Stack`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Stack), [`ConcurrentStack<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) или [`LinkedList<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1)), каждый элемент содержит только значение. В коллекциях, основанных на интерфейсе `IDictionary` (например, классы [`Hashtable`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) и [`SortedList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList) и универсальные классы [`Dictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) и [`SortedList<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2)) или классах [`ConcurrentDictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2), каждый элемент содержит ключ и значение. Класс [`KeyedCollection<TKey, TItem>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) является уникальным, поскольку он представляет собой список значений с встроенными в значения ключами. Поэтому он функционирует как список и как словарь.

Универсальные коллекции являются наилучшим решением для реализации строгой типизации. Однако если язык не поддерживает универсальные шаблоны, пространство имен [`System.Collections`](https://docs.microsoft.com/dotnet/core/api/System.Collections) содержит базовые коллекции, такие как [`CollectionBase`](https://docs.microsoft.com/dotnet/core/api/System.Collections.CollectionBase), [`ReadOnlyCollectionBase`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ReadOnlyCollectionBase) и [`DictionaryBase`](https://docs.microsoft.com/dotnet/core/api/System.Collections.DictionaryBase), которые являются абстрактными базовыми классами с возможностью расширения для создания классов коллекций, которые являются строго типизированными. Если требуется эффективный доступ к многопотоковой коллекции, в пространстве имен [`System.Collections.Concurrent`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) следует использовать универсальные коллекции.

Коллекции могут различаться в зависимости от способов хранения и сортировки элементов, вариантов выполнения поисков и проведения сравнений. Класс [`Queue`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Queue) и универсальный класс [`Queue<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) предоставляют списки по принципу "первым поступил — первым обслужен", а класс [`Stack`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Stack) и универсальный класс [`Stack<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) предоставляют списки по принципу "последним поступил — первым обслужен". Класс [`SortedList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList) и универсальный класс [`SortedList<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) предоставляют сортируемые версии класса [`Hashtable`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) и универсального класса [`Dictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2). Элементы `Hashtable` или `Dictionary<TKey, TValue>` имеют доступ только по ключу элемента, а элементы `SortedList` или [`KeyedCollection<TKey, TItem>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) доступны с помощью ключа или индекса элемента. Индексы во всех коллекциях отсчитываются от нуля за исключением [`Array`](https://docs.microsoft.com/dotnet/core/api/System.Array), допускающего массивы с индексацией не от нуля.

Функция LINQ to Objects позволяет использовать запросы LINQ для доступа к объектам в памяти при условии, что тип объекта реализует интерфейс [`IEnumerable`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable) или [`IEnumerable<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1). Запросы LINQ предоставляют общий шаблон для доступа к данным, являются более четкими и удобочитаемыми, чем стандартные циклы foreach, а также предоставляют возможности фильтрации, сортировки и группировки. LINQ запросы также могут повысить производительность.

## <a name="related-topics"></a>Связанные разделы

Заголовок | Описание
----- | -----------
[`Collections and Data Structures`](index.md) | Описание различных типов коллекций, доступных в .NET Framework, в том числе стеков, очередей, списков, массивов и библиотек.
[`Hashtable and Dictionary Collection Types`](hashtable-and-dictionary-collection-types.md) | Описывает возможности универсальных и неуниверсальных типов словарей на основе хэша.
[`Sorted Collection Types`](sorted-collection-types.md) | Описывает производительность и характеристики отсортированных коллекций.

## <a name="reference"></a>Ссылки

[`System.Collections`](https://docs.microsoft.com/dotnet/core/api/System.Collections)

[`System.Collections.Generic`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)

[`System.Collections.ICollection`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection)

[`System.Collections.Generic.ICollection<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.ICollection-1)

[`System.Collections.IList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IList)

[`System.Collections.Generic.IList<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IList-1)

[`System.Collections.IDictionary`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)

[`System.Collections.Generic.IDictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)

[`System.Linq`](https://docs.microsoft.com/dotnet/core/api/System.Linq)



<!--HONumber=Nov16_HO3-->


