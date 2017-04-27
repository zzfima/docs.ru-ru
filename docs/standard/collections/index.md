---
<<<<<<< HEAD
title: "Коллекции и структуры данных"
description: "Коллекции и структуры данных"
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 9e70255a-c02a-4046-86b7-10c84bab2d38
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 30e53c38bd58e15668e01f2af79defb0a0918192
ms.lasthandoff: 04/05/2017

---

# <a name="collections-and-data-structures"></a>Коллекции и структуры данных

Связанные данные могут обрабатываться более эффективно, если они объединены в коллекцию. Для добавления, удаления и изменения либо отдельных элементов коллекции, либо диапазона элементов коллекции можно использовать класс [System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array) или классы в пространствах имен [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections), [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic) и [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent).

Существует два основных типа коллекций — универсальные и неуниверсальные коллекции. Универсальные коллекции являются строго типизированными во время компиляции. Таким образом, универсальные коллекции обычно обеспечивают более высокую производительность. Универсальные коллекции принимают параметр типа во время создания и не требуют приведение в тип [Object](https://docs.microsoft.com/dotnet/core/api/System.Object) и из него при добавлении или удалении элементов. Неуниверсальные коллекции хранят такие элементы, как [Object](https://docs.microsoft.com/dotnet/core/api/System.Object), и требуют приведения. Неуниверсальные коллекции можно наблюдать в старом коде.

Коллекции в пространстве имен [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) предоставляют эффективные потокобезопасные операции для доступа к элементам коллекций из нескольких потоков.

## <a name="common-collection-features"></a>Общие возможности коллекций

Все коллекции предоставляют методы для добавления, удаления или поиска элементов в коллекции. Кроме того, все коллекции прямо или косвенно реализуют интерфейс [ICollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection) или интерфейс [ICollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.ICollection-1) с совместным использованием следующих функций. 

* **Возможность перечисления коллекции**

   Чтобы обеспечить итерацию по коллекции, коллекции .NET Framework реализуют либо [System.Collections.IEnumerable](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable), либо [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1). Перечислитель может рассматриваться как перемещаемый указатель на любой элемент в коллекции. Оператор `foreach, in` (C#) использует перечислитель, предоставляемый методом `GetEnumerator`, и упрощает обращение с перечислителем. Кроме того, любая коллекция, реализующая [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1), считается запрашиваемым типом, и ее можно запросить с помощью LINQ. Запросы LINQ предоставляют общий шаблон для доступа к данным. Обычно они являются более четкими и удобочитаемыми, чем стандартные циклы foreach, и предлагают возможности фильтрации, упорядочения и группировки. LINQ запросы также могут повысить производительность.
    
* **Возможность копирования содержимого коллекции в массив**

   Все коллекции могут быть скопированы в массив с помощью метода `CopyTo`. Однако порядок элементов в новом массиве зависит от того, в какой последовательности их возвращает перечислитель. Результирующий массив всегда является одномерным массивом с нижней границей, равной нулю.
    
Кроме того, во многих классах коллекций реализованы следующие возможности.

* **Свойства "Емкость и количество элементов"**

   Емкость коллекции — это число элементов, которое она может содержать. Количество элементов коллекции — это число элементов, которое она реально содержит. В некоторых коллекциях емкость или количество элементов скрыты.
    
   Большинство коллекции автоматически увеличивают емкость, если количество элементов достигает предела. Происходит перераспределение памяти, и элементы копируются из старой коллекции в новую. Это уменьшает объем кода, необходимого для использования коллекции. Однако производительность при работе с такой коллекцией может ухудшиться. Например, для [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1), если `Count` меньше `Capacity`, добавление элемента является операцией O(1). Если емкость требуется увеличить для размещения нового элемента, добавление элемента становится операцией O(n), где n — `Count`. Наилучший способ избежать потерь производительности, вызванных множественными перераспределениями, — это установить начальную вместимость, равную предполагаемому размеру коллекции. 
    
   [BitArray](https://docs.microsoft.com/dotnet/core/api/System.Collections.BitArray) является особым случаем; его емкость совпадает с его длиной, которая совпадает с количеством элементов.
    
*   **Согласованная нижняя граница**

   Нижняя граница коллекции — это индекс ее первого элемента. Все индексированные коллекции в пространствах имен [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections) имеют нижнюю границу, равную нулю. Класс [Array](https://docs.microsoft.com/dotnet/core/api/System.Array) имеет нижнюю границу, равную нулю, по умолчанию, но при создании экземпляра класса `Array` с помощью `Array.CreateInstance` может быть определена другая нижняя граница.

*   **Синхронизация для доступа из нескольких потоков** (только классы [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)).

   Для типов неуниверсальных коллекций в пространстве имен [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections) синхронизация обеспечивает определенную степень потокобезопасности. Обычно для выполнения синхронизации используются члены `SyncRoot` и `IsSynchronized`. Эти коллекции не являются потокобезопасными по умолчанию. Если требуется масштабируемый и эффективный многопотоковый доступ к коллекции, используйте один из классов в пространстве имен [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) или рассмотрите возможность применения неизменяемой коллекции. Дополнительные сведения см. в разделе [Потокобезопасные коллекции](threadsafe/index.md).    
    
## <a name="choosing-a-collection"></a>Выбор коллекции 

Как правило, следует использовать универсальные коллекции. В следующей таблице описаны некоторые основные сценарии использования коллекций и классы коллекций, которые можно использовать для этих сценариев. Если вы не работали с универсальными коллекциями, сведения в этой таблице помогут выбрать универсальную коллекцию, лучше всего подходящую для решения ваших задач.

Действие | Возможности универсальной коллекции | Возможности неуниверсальной коллекции
---------- | ---------------------------- | --------------------------------
Хранение элементов в виде пар "ключ-значение" для быстрого поиска по ключу | [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) | [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)
Доступ к элементам по индексу | [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) | [System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array), [System.Collections.ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList)
Использование элементов по принципу FIFO | [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) | [System.Collections.Queue](https://docs.microsoft.com/dotnet/core/api/System.Collections.Queue)
Использование данных по принципу LIFO | [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) | [System.Collections.Stack](https://docs.microsoft.com/dotnet/core/api/System.Collections.Stack)
Последовательный доступ к элементам | [System.Collections.Generic.LinkedList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1) | Рекомендации отсутствуют
Получение уведомлений при удалении элементов из коллекции или добавлении элементов в коллекцию. (реализует [INotifyPropertyChanged](https://docs.microsoft.com/dotnet/core/api/System.ComponentModel.INotifyPropertyChanged) и [INotifyCollectionChanged](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.INotifyCollectionChanged)) | [System.Collections.ObjectModel.ObservableCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.ObservableCollection-1) | Рекомендации отсутствуют
Использование отсортированной коллекции | [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) | [System.Collections.SortedList](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList)
Управление эффективным хранением и доступом к уникальным элементам | [System.Collections.Generic.HashSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.HashSet-1), [System.Collections.Generic.SortedSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedSet-1) | Рекомендации отсутствуют

## <a name="related-topics"></a>Связанные разделы

Заголовок | Описание
----- | -----------
[Выбор класса коллекции](selecting-a-collection-class.md) | Описывает различные коллекций и содержит сведения по выбору коллекции, соответствующей сценарию пользователя.
[Часто используемые типы коллекций](commonly-used-collection-types.md) | Описывает часто используемые типы универсальных и неуниверсальных коллекций, таких как [System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array), [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) и [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2). 
[Когда следует использовать универсальные коллекции](when-to-use-generic-collections.md) | Рассматривает использование типов универсальных коллекций.
[Сравнение и сортировка в коллекциях](comparisons-and-sorts-within-collections.md) | Описывает использование проверок равенства и сортировки в коллекциях.
[Сортируемые типы коллекций](sorted-collection-types.md) | Описывает производительность и характеристики отсортированных коллекций.
[Типы коллекций Hashtable и Dictionary](hashtable-and-dictionary-collection-types.md) | Описывает возможности универсальных и неуниверсальных типов словарей на основе хэша.
[Потокобезопасные коллекции](threadsafe/index.md) | Описывает такие типы коллекций, как [System.Collections.Concurrent.BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) и [System.Collections.Concurrent.ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1), поддерживающие безопасный и эффективный одновременный доступ из нескольких потоков.

## <a name="reference"></a>Ссылка

[System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array)

[System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)

[System.Collections.Specialized](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized)

[System.Linq](https://docs.microsoft.com/dotnet/core/api/System.Linq)
  

=======
title: "Коллекции и структуры данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "группировка данных в коллекциях"
  - "объекты [платформа .NET Framework], группировка в коллекциях"
  - "класс Array, группировка данных в коллекциях"
  - "работа с потоками [платформа .NET Framework], безопасность"
  - "Collections - классы"
  - "коллекции [платформа .NET Framework]"
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
caps.latest.revision: 36
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 35
---
# Коллекции и структуры данных
Связанные данные могут обрабатываться более эффективно, если они объединены в коллекцию. Можно использовать <xref:System.Array?displayProperty=fullName> класс или классы в <xref:System.Collections>, <xref:System.Collections.Generic>, <xref:System.Collections.Concurrent>, System.Collections.Immutable пространства имен для добавления, удаления и изменения либо отдельных элементов или диапазон элементов в коллекции.  
  
 Существует два основных типа коллекций — универсальные и неуниверсальные коллекции. Универсальные коллекции были добавлены в платформе .NET Framework 2.0 и являются строготипизированными во время компиляции. Таким образом, универсальные коллекции обычно обеспечивают более высокую производительность. Универсальные коллекции принимают параметр типа во время создания и не требуют приведение в тип <xref:System.Object> и из него при добавлении или удалении элементов.  Кроме того, большая часть универсальных коллекций поддерживается в приложениях [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)]. Неуниверсальные коллекции хранят такие элементы, как <xref:System.Object>, требуют приведения и большинство не поддерживаются для [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] разработки приложений. Однако неуниверсальные коллекции можно наблюдать в старом коде.  
  
 Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], в коллекции <xref:System.Collections.Concurrent> пространства имен предоставляют эффективный потокобезопасные операции для доступа к элементам коллекций из нескольких потоков. Неизменяемые классы коллекций в пространстве имен System.Collections.Immutable ([пакет NuGet](https://www.nuget.org/packages/System.Collections.Immutable)) являются по своей природе потокобезопасными, поскольку операции выполняются с копией исходной коллекции и не может изменяться исходной коллекции.  
  
   
  
<a name="BKMK_Commoncollectionfeatures"></a>   
## <a name="common-collection-features"></a>Общие возможности коллекций  
 Все коллекции предоставляют методы для добавления, удаления или поиска элементов в коллекции. Кроме того, все коллекции прямо или косвенно реализуют <xref:System.Collections.ICollection> интерфейс или <xref:System.Collections.Generic.ICollection%601> интерфейс совместным использованием следующих функций:  
  
-   **Возможность перечисления коллекции**  
  
     Коллекции .NET framework реализуют либо <xref:System.Collections.IEnumerable?displayProperty=fullName> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> выполнить итерацию по коллекции. Перечислитель может рассматриваться как перемещаемый указатель на любой элемент в коллекции. [Foreach в](../Topic/foreach,%20in%20\(C%23%20Reference\).md) инструкции и [For Each... Следующий оператор](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md) использовать предоставляемые <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод и скрыть сложность обращения с перечислителем. Кроме того, любая коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> считается *запрашиваемым типом* и можно запросить с помощью LINQ. Запросы LINQ предоставляют общий шаблон для доступа к данным. Обычно они являются более четкими и удобочитаемыми, чем стандартные циклы `foreach`, и предлагают возможности фильтрации, упорядочения и группировки. LINQ запросы также могут повысить производительность. Дополнительные сведения см. в разделе [LINQ to Objects](../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-objects.md), [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md) и [введение в запросы LINQ (C#)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
-   **Возможность копирования содержимого коллекции в массив**  
  
     Все коллекции могут быть скопированы в массив с помощью **CopyTo** метод; Однако порядок элементов в новом массиве зависит от последовательности, в которой их Возвращает перечислитель. Результирующий массив всегда является одномерным массивом с нижней границей, равной нулю.  
  
 Кроме того, во многих классах коллекций реализованы следующие возможности.  
  
-   **Свойства "Емкость и количество элементов"**  
  
     Емкость коллекции — это число элементов, которое она может содержать. Количество элементов коллекции — это число элементов, которое она реально содержит. В некоторых коллекциях емкость или количество элементов скрыты.  
  
     Большинство коллекции автоматически увеличивают емкость, если количество элементов достигает предела. Происходит перераспределение памяти, и элементы копируются из старой коллекции в новую. Это уменьшает объем кода, необходимого для использования коллекции. Однако производительность при работе с такой коллекцией может ухудшиться. Например, для <xref:System.Collections.Generic.List%601>, если <xref:System.Collections.Generic.List%601.Count%2A> — меньше, чем <xref:System.Collections.Generic.List%601.Capacity%2A>, добавление элемента является операцией o(1). Если емкость требуется увеличить для размещения нового элемента, добавление элемента становится операцией O(n), где n — <xref:System.Collections.Generic.List%601.Count%2A>. Наилучший способ избежать потерь производительности, вызванных множественными перераспределениями, — это установить начальную вместимость, равную предполагаемому размеру коллекции.  
  
     <xref:System.Collections.BitArray> является особым случаем; его емкость совпадает с его длиной, которая совпадает с количеством элементов.  
  
-   **Согласованная нижняя граница**  
  
     Нижняя граница коллекции — это индекс ее первого элемента. Все индексированные коллекции в пространствах имен <xref:System.Collections> имеют нижнюю границу, равную нулю. <xref:System.Array> имеет нижнюю границу, равную нулю, по умолчанию, но другая нижняя граница можно задать при создании экземпляра **массива** класса <xref:System.Array.CreateInstance%2A?displayProperty=fullName>.  
  
-   **Синхронизация для доступа из нескольких потоков** (только классы <xref:System.Collections>).  
  
     Типы неуниверсальных коллекций в <xref:System.Collections> пространство имен обеспечивает определенную степень потокобезопасности при синхронизации; обычно предоставляется через <xref:System.Collections.ICollection.SyncRoot%2A> и <xref:System.Collections.ICollection.IsSynchronized%2A> члены. Эти коллекции не являются потокобезопасными по умолчанию. Если требуется масштабируемый и эффективный многопотоковый доступ к коллекции, используйте один из классов в пространстве имен <xref:System.Collections.Concurrent> или рассмотрите возможность применения неизменяемой коллекции. Дополнительные сведения см. в разделе [Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md).  
  
<a name="BKMK_Choosingacollection"></a>   
## <a name="choosing-a-collection"></a>Выбор коллекции  
 Как правило, следует использовать универсальные коллекции. В следующей таблице описаны некоторые основные сценарии использования коллекций и классы коллекций, которые можно использовать для этих сценариев. Если вы не работали с универсальными коллекциями, сведения в этой таблице помогут выбрать универсальную коллекцию, лучше всего подходящую для решения ваших задач.  
  
|||||  
|-|-|-|-|  
|Действие|Возможности универсальной коллекции|Возможности неуниверсальной коллекции|Возможности потокобезопасной и неизменяемой коллекции|  
|Хранение элементов в виде пар "ключ-значение" для быстрого поиска по ключу|<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName></TKey, TValue>|<xref:System.Collections.Hashtable><br /><br /> (Коллекция пар "ключ-значение", которые упорядочены по хэш-коду ключа.)|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>\</TKey, TValue><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=fullName>\</TKey, TValue><br /><br /> [Класс ImmutableDictionary (TKey, TValue)](../Topic/ImmutableDictionary\(TKey,%20TValue\)%20Class.md)|  
|Доступ к элементам по индексу|<xref:System.Collections.Generic.List%601?displayProperty=fullName>|<xref:System.Array?displayProperty=fullName><br /><br /> <xref:System.Collections.ArrayList?displayProperty=fullName>|[Класс ImmutableList(T)](../Topic/ImmutableList\(T\)%20Class.md)<br /><br /> [Класс ImmutableArray](../Topic/ImmutableArray%20Class.md)|  
|Использование элементов по принципу FIFO|<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>|<xref:System.Collections.Queue?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName><br /><br /> [Класс ImmutableQueue(T)](../Topic/ImmutableQueue\(T\)%20Class.md)|  
|Использование данных по принципу LIFO|<xref:System.Collections.Generic.Stack%601?displayProperty=fullName>|<xref:System.Collections.Stack?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName><br /><br /> [Класс ImmutableStack(T)](../Topic/ImmutableStack\(T\)%20Class.md)|  
|Последовательный доступ к элементам|<xref:System.Collections.Generic.LinkedList%601?displayProperty=fullName>|Рекомендации отсутствуют|Рекомендации отсутствуют|  
|Получение уведомлений при удалении элементов из коллекции или добавлении элементов в коллекцию. (реализует <xref:System.ComponentModel.INotifyPropertyChanged> и <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>)|<xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>|Рекомендации отсутствуют|Рекомендации отсутствуют|  
|Отсортированная коллекция|<xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>\</TKey, TValue>|<xref:System.Collections.SortedList?displayProperty=fullName>|[Класс ImmutableSortedDictionary (TKey, TValue)](../Topic/ImmutableSortedDictionary\(TKey,%20TValue\)%20Class.md)<br /><br /> [Класс ImmutableSortedSet(T)](../Topic/ImmutableSortedSet\(T\)%20Class.md)|  
|Набор для математических функций|<xref:System.Collections.Generic.HashSet%601?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>|Рекомендации отсутствуют|[Класс ImmutableHashSet(T)](../Topic/ImmutableHashSet\(T\)%20Class.md)<br /><br /> [Класс ImmutableSortedSet(T)](../Topic/ImmutableSortedSet\(T\)%20Class.md)|  
  
<a name="BKMK_RelatedTopics"></a>   
## <a name="related-topics"></a>Связанные разделы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Выбор класса коллекции](../../../docs/standard/collections/selecting-a-collection-class.md)|Описывает различные коллекций и содержит сведения по выбору коллекции, соответствующей сценарию пользователя.|  
|[Часто используемые типы коллекций](../../../docs/standard/collections/commonly-used-collection-types.md)|Описывает типы часто используемых универсальных и неуниверсальных коллекций, таких как <xref:System.Array?displayProperty=fullName>, <xref:System.Collections.Generic.List%601?displayProperty=fullName>, и <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>.\</TKey, TValue>|  
|[Когда следует использовать универсальные коллекции](../../../docs/standard/collections/when-to-use-generic-collections.md)|Рассматривает использование типов универсальных коллекций.|  
|[Сравнение и сортировка в коллекциях](../../../docs/standard/collections/comparisons-and-sorts-within-collections.md)|Описывает использование проверок равенства и сортировки в коллекциях.|  
|[Отсортированные типы коллекций](../../../docs/standard/collections/sorted-collection-types.md)|Описывает производительность и характеристики отсортированных коллекций.|  
|[Типы коллекций Hashtable и Dictionary](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|Описывает возможности универсальных и неуниверсальных типов словарей на основе хэша.|  
|[Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md)|Описывает типы коллекций, такие как <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> и <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName> , поддерживающие безопасный и эффективный одновременный доступ из нескольких потоков.|  
|System.Collections.Immutable|Приводятся вводные сведения о неизменяемых коллекциях и ссылки на типы коллекций.|  
  
<a name="BKMK_Reference"></a>   
## <a name="reference"></a>Ссылка  
 <xref:System.Array?displayProperty=fullName>  
  
 <xref:System.Collections?displayProperty=fullName>  
  
 <xref:System.Collections.Concurrent?displayProperty=fullName>  
  
 <xref:System.Collections.Generic?displayProperty=fullName>  
  
 <xref:System.Collections.Specialized?displayProperty=fullName>  
  
 <xref:System.Linq?displayProperty=fullName>  
  
 System.Collections.Immutable
>>>>>>> a8ea58d... fix build errors
