---
title: "Выбор класса коллекции"
description: "Выбор класса коллекции"
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0a60fca7-e082-48d4-9dda-30b0d3e67ec7
translationtype: Human Translation
ms.sourcegitcommit: 763433b00ae7d01cfa0c7fa250f51d23a95f6f15
ms.openlocfilehash: d174d0cb910035340fb317521f3ad930d16853c2
ms.lasthandoff: 01/18/2017

---

# <a name="selecting-a-collection-class"></a>Выбор класса коллекции

Внимательно относитесь к выбору класса коллекции. Неправильный тип может ограничить возможности использования коллекции. Универсальные и параллельные версии коллекций предпочтительны из-за повышенной безопасности типов и других усовершенствований. Как правило, не рекомендуется использовать типы в пространстве имен "System.Collections", если приложение не создается специально для .NET Framework версии 1.1. 

Ответьте на следующие вопросы.

* Нужен ли вам последовательный список, элемент которого обычно удаляется сразу после извлечения его значения? 

    * Если да, то рассмотрите возможность использования универсального класса [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1), если требуется обработка по принципу "первым поступил — первым обслужен" (FIFO). Рассмотрите возможность использования универсального класса [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1), если требуется обработка по принципу "последним поступил — первым обслужен" (LIFO). Для безопасного доступа из нескольких потоков используйте параллельные версии [System.Collections.Concurrent.ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) и [System.Collections.Concurrent.ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1).
    
    * Если нет, то следует использовать другие коллекции.
    
* Нужен ли доступ к элементам в определенном порядке (FIFO, LIFO) или в произвольным порядке?

    * Универсальные классы [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) и [System.Collections.Concurrent.ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) обеспечивают доступ по принципу FIFO. Дополнительные сведения см. в разделе [Преимущества использования потокобезопасных коллекций](threadsafe/when-to-use-a-thread-safe-collection.md).
    
    * Универсальные классы [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) и [System.Collections.Concurrent.ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) обеспечивают доступ по принципу LIFO. Дополнительные сведения см. в разделе [Преимущества использования потокобезопасных коллекций](threadsafe/when-to-use-a-thread-safe-collection.md).
    
    * Универсальный класс [System.Collections.Generic.LinkedList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1) предоставляет последовательный доступ от начала к концу списка или наоборот.
    
* Требуется ли доступ к каждому элементу по индексу? 

    * Класс [System.Collections.Specialized.StringCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringCollection) и универсальный класс [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) предоставляют доступ к своим элементам с помощью отсчитываемого от нуля индекса элемента. 
    
    * Классы [System.Collections.Specialized.ListDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.ListDictionary) и [System.Collections.Specialized.StringDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringDictionary), а также универсальные классы [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) и [System.Collections.Generic.SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) предоставляют доступ к своим элементам с помощью ключа элемента.
    
    * Классы [System.Collections.Specialized.NameObjectCollectionBase](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.NameObjectCollectionBase) и [System.Collections.Specialized.NameValueCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.NameValueCollection), а также универсальные классы [System.Collections.ObjectModel.KeyedCollection&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) и [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) предоставляют доступ к своим элементам либо с помощью отсчитываемого от нуля индекса элемента, либо с помощью ключа элемента.
    
* Будет ли каждый элемент содержать только одно значение, сочетание из одного ключа и одного значения или сочетание из одного ключа и нескольких значений? 

    * Одно значение: используйте любую коллекцию, основанную на универсальном интерфейсе [System.Collections.Generic.IList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IList-1).
    
    * Один ключ и одно значение: используйте любую коллекцию, основанную на универсальном интерфейсе [System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2).
    
    * Одно значение с внедренным ключом: используйте универсальный класс [System.Collections.ObjectModel.KeyedCollection&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2).
    
    * Один ключ и несколько значений: используйте класс [System.Collections.Specialized.NameValueCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.NameValueCollection).
    
* Требуется ли сортировать элементы в порядке, отличном от порядка их поступления? 

    * Класс [System.Collections.Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) сортирует свои элементы по их хэш-кодам.
    
    * Универсальные классы [System.Collections.Generic.SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) и [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) сортируют свои элементы по ключам на основе реализации интерфейса [System.Collections.IComparer](https://docs.microsoft.com/dotnet/core/api/System.Collections.IComparer) и универсального интерфейса [System.Collections.Generic.IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1).
    
    * Универсальный класс [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) предоставляет метод `Sort`, который принимает реализацию универсального интерфейса `IComparer<T>` в качестве параметра.
    
* Требуются ли вам коллекции, принимающие только строки? 

    * [StringCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringCollection) (на основе [System.Collections.IList](https://docs.microsoft.com/dotnet/core/api/System.Collections.IList)) и [StringDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringDictionary) (на основе [System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)) находятся в пространстве имен [System.Collections.Specialized](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized). 
    
    * Кроме того, можно использовать любой из универсальных классов коллекций в пространстве имен [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic) как строго типизированную строковую коллекцию, указав класс `String` в качестве аргумента универсального типа.
    
## <a name="linq-to-objects"></a>LINQ to Objects

Функция LINQ to Objects позволяет использовать запросы LINQ для доступа к объектам в памяти при условии, что тип объекта реализует интерфейс [System.Collections.IEnumerable](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable) или [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1). Запросы LINQ запросы предоставляют общий шаблон для доступа к данным, являются более четкими и удобочитаемыми, чем стандартные циклы foreach, а также предоставляют возможности фильтрации, сортировки и группировки. Дополнительные сведения см. в разделе [Синтаксис LINQ](../../csharp/linq/index.md).

## <a name="see-also"></a>См. также

[System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)

[System.Collections.Specialized](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized)

[System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)

[Потокобезопасные коллекции](threadsafe/index.md)

