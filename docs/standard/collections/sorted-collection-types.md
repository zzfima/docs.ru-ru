---
title: "Отсортированные типы коллекций"
description: "Отсортированные типы коллекций"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bdc9c13e-e56a-433b-a293-c92364f6e9cb
translationtype: Human Translation
ms.sourcegitcommit: 149086110d7470d97e1ab3e5969269626290b523
ms.openlocfilehash: a5f6e2ef7f765dccf1fee0e2de60dea8aec003b9

---

# <a name="sorted-collection-types"></a>Отсортированные типы коллекций  
 
 Класс [System.Collections.SortedList](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList) универсальный класс [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2), а также универсальный класс [System.Collections.Generic.SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) схожи с классом [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) и универсальным классом [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) в том, что реализуют интерфейс [IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary), однако сортировку своих элементов они выполняют по ключам. Кроме того, в них отсутствуют функции вставки O(1) и извлечения характеристик хэш-таблиц. Эти три класса имеют ряд схожих свойств:  

 *   Все три класса реализуют интерфейс [System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary). Два универсальных класса из них также реализуют универсальный интерфейс [System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2).  
 
 *   Каждый элемент является парой ключ-значение для перечисления.   
  
> [!NOTE]  
> При перечислении неуниверсальный класс [SortedList](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList) возвращает объект [DictionaryEntry](https://docs.microsoft.com/dotnet/core/api/System.Collections.DictionaryEntry), тогда как два универсальных класса возвращают объекты [KeyValuePair&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.KeyValuePair-2).  
   
*   Элементы сортируются в соответствии с реализацией [System.Collections.IComparer](https://docs.microsoft.com/dotnet/core/api/System.Collections.IComparer) (для неуниверсального класса `SortedList`) или реализацией [System.Collections.Generic.IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1) (для двух универсальных классов).  
   
 *   Каждый класс предоставляет свойства, которые возвращают коллекции, содержащие только ключи или только значения.  
   
В таблице ниже перечислены некоторые различия между двумя классами отсортированных списков и классом [SortedDictionary<TKey, TValue>](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2).  
   
 Неуниверсальный класс `SortedList` и универсальный класс `SortedList<TKey, TValue>`. | Универсальный класс `SortedDictionary<TKey, TValue>`.  
 --------------------------------------------------------------------------------- | ------------------------------  
 Свойства, возвращающие ключи и значения, индексируются, что позволяет выполнять эффективное индексированное извлечение. | Неиндексированное извлечение.  
 Извлечение — O(log n). | Извлечение — O(log n).  
 Вставка и удаление, как правило, являются O(n); тем не менее вставка является O(1) для данных, которые уже отсортированы, чтобы каждый элемент добавлялся в конец списка. (Предполагается, что изменение размера не требуется.) | Вставка и удаление являются O(log n).  
 Использует меньше памяти, чем `SortedDictionary<TKey, TValue>`. | Использует больше памяти, чем неуниверсальный класс `SortedList` и универсальный класс `SortedList<TKey, TValue>`.  
  
 Для отсортированных списков или словарей, которые должны быть доступны одновременно из нескольких потоков, можно добавить логику сортировки в класс, производный от класса [ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2).  
  
 > [!NOTE]  
 > Для значений, содержащих собственные ключи (например, записи о сотрудниках, содержащие идентификатор сотрудника), можно создать коллекцию с ключом, имеющую некоторые характеристики списка и словаря, путем создания класса, производного от универсального класса [KeyedCollection&lt;TKey, TItem&gt;]().  
   
 Класс [SortedSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedSet-1) предоставляет самобалансируемое дерево, в котором данные хранятся в отсортированном порядке после операций вставки, удаления и поиска. Этот класс и класс [HashSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.HashSet-1) реализуют интерфейс [ISet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.ISet-1).  
   
## <a name="see-also"></a>См. также  
  
[System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)  
   
[System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)  
   
[ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2)  
 
[Часто используемые типы коллекций](commonly-used-collection-types.md) 



<!--HONumber=Nov16_HO1-->


