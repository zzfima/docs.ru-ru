---
title: "Коллекции и структуры данных | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grouping data in collections
- objects [.NET Framework], grouping in collections
- Array class, grouping data in collections
- threading [.NET Framework], safety
- Collections classes
- collections [.NET Framework]
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
caps.latest.revision: 36
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 27c475b8d29eb295bb3d6be24aa9ee9188f5c114
ms.contentlocale: ru-ru
ms.lasthandoff: 04/08/2017

---
# <a name="collections-and-data-structures"></a>Коллекции и структуры данных
Связанные данные могут обрабатываться более эффективно, если они объединены в коллекцию. Для добавления, удаления и изменения отдельных элементов или диапазона элементов коллекции можно использовать класс <xref:System.Array?displayProperty=fullName> или классы в пространствах имен <xref:System.Collections>, <xref:System.Collections.Generic>, <xref:System.Collections.Concurrent> и System.Collections.Immutable.  
  
 Существует два основных типа коллекций — универсальные и неуниверсальные коллекции. Универсальные коллекции были добавлены в платформе .NET Framework 2.0 и являются строготипизированными во время компиляции. Таким образом, универсальные коллекции обычно обеспечивают более высокую производительность. Универсальные коллекции принимают параметр типа во время создания и не требуют приведение в тип <xref:System.Object> и из него при добавлении или удалении элементов.  Кроме того, большая часть универсальных коллекций поддерживается в приложениях [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)]. Неуниверсальные коллекции хранят элементы как <xref:System.Object>, требуя приведения. Большая их часть не подходит для разработки приложений [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)]. Однако неуниверсальные коллекции можно наблюдать в старом коде.  
  
 Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] коллекции в пространстве имен <xref:System.Collections.Concurrent> предоставляют эффективные потокобезопасные операции для доступа к элементам коллекций из нескольких потоков. Неизменяемые классы коллекций в пространстве имен System.Collections.Immutable ([пакет NuGet](https://www.nuget.org/packages/System.Collections.Immutable)) являются по своей природе потокобезопасными, поскольку операции выполняются с копией исходной коллекции, а исходная коллекция неизменяема.  
  
  
<a name="BKMK_Commoncollectionfeatures"></a>   
## <a name="common-collection-features"></a>Общие возможности коллекций  
 Все коллекции предоставляют методы для добавления, удаления или поиска элементов в коллекции. Кроме того, всем коллекциям, которые прямо или косвенно реализуют интерфейс <xref:System.Collections.ICollection> или <xref:System.Collections.Generic.ICollection%601>, присущи следующие возможности:  
  
-   **Возможность перечисления коллекции**  
  
     Чтобы обеспечить итерацию по коллекции, коллекции .NET Framework реализуют либо <xref:System.Collections.IEnumerable?displayProperty=fullName>, либо <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>. Перечислитель может рассматриваться как перемещаемый указатель на любой элемент в коллекции. Операторы [foreach, in](~/docs/csharp/language-reference/keywords/foreach-in.md) и [For Each...Next Statement](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) используют перечислитель, предоставляемый методом <xref:System.Collections.IEnumerable.GetEnumerator%2A>, и существенно упрощают работу с перечислителем. Кроме того, любая коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>, относится к *запрашиваемому типу*, и ее можно запросить с помощью LINQ. Запросы LINQ предоставляют общий шаблон для доступа к данным. Обычно они являются более четкими и удобочитаемыми, чем стандартные циклы `foreach`, и предлагают возможности фильтрации, упорядочения и группировки. LINQ запросы также могут повысить производительность. Дополнительные сведения см. в статьях [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9), [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md) и [Введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
-   **Возможность копирования содержимого коллекции в массив**  
  
     Все коллекции могут быть скопированы в массив с помощью метода **CopyTo**. Однако порядок элементов в новом массиве зависит от того, в какой последовательности их возвращает перечислитель. Результирующий массив всегда является одномерным массивом с нижней границей, равной нулю.  
  
 Кроме того, во многих классах коллекций реализованы следующие возможности.  
  
-   **Свойства "Емкость и количество элементов"**  
  
     Емкость коллекции — это число элементов, которое она может содержать. Количество элементов коллекции — это число элементов, которое она реально содержит. В некоторых коллекциях емкость или количество элементов скрыты.  
  
     Большинство коллекции автоматически увеличивают емкость, если количество элементов достигает предела. Происходит перераспределение памяти, и элементы копируются из старой коллекции в новую. Это уменьшает объем кода, необходимого для использования коллекции. Однако производительность при работе с такой коллекцией может ухудшиться. Например, в случае с <xref:System.Collections.Generic.List%601>, если значение <xref:System.Collections.Generic.List%601.Count%2A> меньше значения <xref:System.Collections.Generic.List%601.Capacity%2A>, добавление объекта считается операцией O(1). Если емкость требуется увеличить для размещения нового элемента, добавление элемента становится операцией O(n), где n — это <xref:System.Collections.Generic.List%601.Count%2A>. Наилучший способ избежать потерь производительности, вызванных множественными перераспределениями, — это установить начальную вместимость, равную предполагаемому размеру коллекции.  
  
     <xref:System.Collections.BitArray> — особый случай. Его емкость совпадает с его длиной, которая, в свою очередь, совпадает с количеством элементов.  
  
-   **Согласованная нижняя граница**  
  
     Нижняя граница коллекции — это индекс ее первого элемента. Все индексированные коллекции в пространствах имен <xref:System.Collections> имеют нижнюю границу, равную нулю. <xref:System.Array> имеет нижнюю границу, равную нулю, по умолчанию, но при создании экземпляра класса **Array** с помощью <xref:System.Array.CreateInstance%2A?displayProperty=fullName> может быть определена другая нижняя граница.  
  
-   **Синхронизация для доступа из нескольких потоков** (только классы <xref:System.Collections>).  
  
     Типы неуниверсальных коллекций в пространстве имен <xref:System.Collections> обеспечивают некоторую потокобезопасность с помощью синхронизации. Обычно они предоставляются через члены <xref:System.Collections.ICollection.SyncRoot%2A> и <xref:System.Collections.ICollection.IsSynchronized%2A>. Эти коллекции не являются потокобезопасными по умолчанию. Если вам нужен масштабируемый и эффективный многопотоковый доступ к коллекции, используйте один из классов в пространстве имен <xref:System.Collections.Concurrent> или рассмотрите возможность применения неизменяемой коллекции. Дополнительные сведения см. в разделе [Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md).  
  
<a name="BKMK_Choosingacollection"></a>   
## <a name="choosing-a-collection"></a>Выбор коллекции  
 Как правило, следует использовать универсальные коллекции. В следующей таблице описаны некоторые основные сценарии использования коллекций и классы коллекций, которые можно использовать для этих сценариев. Если вы не работали с универсальными коллекциями, сведения в этой таблице помогут выбрать универсальную коллекцию, лучше всего подходящую для решения ваших задач.  
<!-- todo: All code-formatted API refs in the table need to be changed into links -->  
|Действие|Возможности универсальной коллекции|Возможности неуниверсальной коллекции|Возможности потокобезопасной и неизменяемой коллекции|  
|-|-|-|-|  
|Хранение элементов в виде пар "ключ-значение" для быстрого поиска по ключу|<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>|<xref:System.Collections.Hashtable><br /><br /> (Коллекция пар "ключ-значение", которые упорядочены по хэш-коду ключа.)|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=fullName><br /><br /> `ImmutableDictionary(TKey, TValue) Class`|  
|Доступ к элементам по индексу|<xref:System.Collections.Generic.List%601?displayProperty=fullName>|<xref:System.Array?displayProperty=fullName><br /><br /> <xref:System.Collections.ArrayList?displayProperty=fullName>|`ImmutableList(T) Class`<br /><br /> `ImmutableArray Class`|  
|Использование элементов по принципу FIFO|<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>|<xref:System.Collections.Queue?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName><br /><br /> `ImmutableQueue(T) Class`|  
|Использование данных по принципу LIFO|<xref:System.Collections.Generic.Stack%601?displayProperty=fullName>|<xref:System.Collections.Stack?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName><br /><br /> `ImmutableStack(T) Class`|  
|Последовательный доступ к элементам|<xref:System.Collections.Generic.LinkedList%601?displayProperty=fullName>|Рекомендации отсутствуют|Рекомендации отсутствуют|  
|Получение уведомлений при удалении элементов из коллекции или добавлении элементов в коллекцию. (реализует <xref:System.ComponentModel.INotifyPropertyChanged> и <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>)|<xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>|Рекомендации отсутствуют|Рекомендации отсутствуют|  
|Отсортированная коллекция|<xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>|<xref:System.Collections.SortedList?displayProperty=fullName>|`ImmutableSortedDictionary(TKey, TValue) Class`<br /><br /> `ImmutableSortedSet(T) Class`|  
|Набор для математических функций|<xref:System.Collections.Generic.HashSet%601?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>|Рекомендации отсутствуют|`ImmutableHashSet(T) Class`<br /><br /> `ImmutableSortedSet(T) Class`|  
  
<a name="BKMK_RelatedTopics"></a>   
## <a name="related-topics"></a>Связанные разделы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Выбор класса коллекции](../../../docs/standard/collections/selecting-a-collection-class.md)|Описывает различные коллекций и содержит сведения по выбору коллекции, соответствующей сценарию пользователя.|  
|[Часто используемые типы коллекций](../../../docs/standard/collections/commonly-used-collection-types.md)|Описывает распространенные типы универсальных и неуниверсальных коллекций, например <xref:System.Array?displayProperty=fullName>, <xref:System.Collections.Generic.List%601?displayProperty=fullName> и <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>.|  
|[Когда следует использовать универсальные коллекции](../../../docs/standard/collections/when-to-use-generic-collections.md)|Рассматривает использование типов универсальных коллекций.|  
|[Сравнение и сортировка в коллекциях](../../../docs/standard/collections/comparisons-and-sorts-within-collections.md)|Описывает использование проверок равенства и сортировки в коллекциях.|  
|[Отсортированные типы коллекций](../../../docs/standard/collections/sorted-collection-types.md)|Описывает производительность и характеристики отсортированных коллекций.|  
|[Типы коллекций Hashtable и Dictionary](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|Описывает возможности универсальных и неуниверсальных типов словарей на основе хэша.|  
|[Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md)|Описывает такие типы коллекций, как <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> и <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>, которые поддерживают безопасный и эффективный одновременный доступ из нескольких потоков.|  
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
