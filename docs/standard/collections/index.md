---
title: "Коллекции и структуры данных"
description: "Коллекции и структуры данных"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9e70255a-c02a-4046-86b7-10c84bab2d38
translationtype: Human Translation
ms.sourcegitcommit: cfe65fcba1b3fdc09ffcac704a760d8ce29ea60b
ms.openlocfilehash: 3f2831f21654d9eb1523cd80166b674e7c41d8bb

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
  



<!--HONumber=Nov16_HO1-->


