---
title: Выбор класса коллекции
ms.date: 03/18/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- last-in-first-out collections
- first-in-first-out collections
- collections [.NET Framework], selecting collection class
- indexed collections
- Collections classes
- grouping data in collections, selecting collection class
ms.assetid: ba049f9a-ce87-4cc4-b319-3f75c8ddac8a
ms.openlocfilehash: fb03200c810290c970f7aa56a0e15d385aca7ca8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711354"
---
# <a name="selecting-a-collection-class"></a>Выбор класса коллекции

Внимательно относитесь к выбору класса коллекции. Неправильный тип может ограничить возможности использования коллекции.  

> [!IMPORTANT]
> Не используйте такие типы в пространстве имен <xref:System.Collections>. Рекомендуется использовать универсальные и параллельные версии коллекций из-за более высокой безопасности типов и других усовершенствований.  

 Ответьте на следующие вопросы.  
  
- Нужен ли вам последовательный список, элемент которого обычно удаляется сразу после извлечения его значения?  
  
  - Если да, то рассмотрите возможность использования класса <xref:System.Collections.Queue> или универсального класса <xref:System.Collections.Generic.Queue%601>, если требуется обработка по принципу "первым поступил — первым обслужен" (FIFO). Рассмотрите возможность использования класса <xref:System.Collections.Stack> или универсального класса <xref:System.Collections.Generic.Stack%601>, если требуется обработка по принципу "последним поступил — первым обслужен" (LIFO). Для безопасного доступа из нескольких потоков используйте параллельные версии классов <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
  - Если нет, то следует использовать другие коллекции.  
  
- Нужен ли доступ к элементам в определенном порядке (FIFO, LIFO) или в произвольным порядке?  
  
  - Класс <xref:System.Collections.Queue> и универсальный класс <xref:System.Collections.Generic.Queue%601> или <xref:System.Collections.Concurrent.ConcurrentQueue%601> предоставляют доступ в порядке FIFO. Дополнительные сведения см. в разделе [Преимущества использования потокобезопасных коллекций](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).  
  
  - Класс <xref:System.Collections.Stack> и универсальный класс <xref:System.Collections.Generic.Stack%601> или <xref:System.Collections.Concurrent.ConcurrentStack%601> предоставляют доступ в порядке LIFO. Дополнительные сведения см. в разделе [Преимущества использования потокобезопасных коллекций](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).  
  
  - Универсальный класс <xref:System.Collections.Generic.LinkedList%601> предоставляет последовательный доступ от начала к концу списка или наоборот.  
  
- Требуется ли доступ к каждому элементу по индексу?  
  
  - Классы <xref:System.Collections.ArrayList> и <xref:System.Collections.Specialized.StringCollection> и универсальный класс <xref:System.Collections.Generic.List%601> предоставляют доступ к элементам по отсчитываемому от нуля индексу элемента.  
  
  - Классы <xref:System.Collections.Hashtable>, <xref:System.Collections.SortedList>, <xref:System.Collections.Specialized.ListDictionary> и <xref:System.Collections.Specialized.StringDictionary> и универсальные классы <xref:System.Collections.Generic.Dictionary%602> и <xref:System.Collections.Generic.SortedDictionary%602> предоставляют доступ к элементам по ключу элемента.  
  
  - Классы <xref:System.Collections.Specialized.NameObjectCollectionBase> и <xref:System.Collections.Specialized.NameValueCollection> и универсальные классы <xref:System.Collections.ObjectModel.KeyedCollection%602> и <xref:System.Collections.Generic.SortedList%602> предоставляют доступ к элементам по отсчитываемому от нуля индексу или по ключу элемента.  
  
- Будет ли каждый элемент содержать только одно значение, сочетание из одного ключа и одного значения или сочетание из одного ключа и нескольких значений?  
  
  - Одно значение: используйте любую коллекцию, основанную на интерфейсе <xref:System.Collections.IList> или на универсальном интерфейсе <xref:System.Collections.Generic.IList%601>.  
  
  - Один ключ и одно значение: используйте любую коллекцию, основанную на интерфейсе <xref:System.Collections.IDictionary> или на универсальном интерфейсе <xref:System.Collections.Generic.IDictionary%602>.  
  
  - Одно значение с внедренным ключом: используйте универсальный класс <xref:System.Collections.ObjectModel.KeyedCollection%602>.  
  
  - Один ключ и несколько значений: используйте класс <xref:System.Collections.Specialized.NameValueCollection>.  
  
- Требуется ли сортировать элементы в порядке, отличном от порядка их поступления?  
  
  - Класс <xref:System.Collections.Hashtable> сортирует элементы по хэш-коду.  
  
  - В классе <xref:System.Collections.SortedList> и универсальных классах <xref:System.Collections.Generic.SortedList%602> и <xref:System.Collections.Generic.SortedDictionary%602> элементы сортируются по ключу. Порядок сортировки зависит от реализации интерфейса <xref:System.Collections.IComparer> для класса <xref:System.Collections.SortedList> и от реализации универсального интерфейса <xref:System.Collections.Generic.IComparer%601> для универсальных классов <xref:System.Collections.Generic.SortedList%602> и <xref:System.Collections.Generic.SortedDictionary%602>. Из двух универсальных типов <xref:System.Collections.Generic.SortedDictionary%602> обеспечивает более высокую производительность, чем <xref:System.Collections.Generic.SortedList%602>, но <xref:System.Collections.Generic.SortedList%602> потребляет меньше памяти.  
  
  - Класс <xref:System.Collections.ArrayList> предоставляет метод <xref:System.Collections.ArrayList.Sort%2A>, который принимает реализацию <xref:System.Collections.IComparer> в качестве параметра. Его универсальный аналог, универсальный класс <xref:System.Collections.Generic.List%601>, предоставляет метод <xref:System.Collections.Generic.List%601.Sort%2A>, который принимает реализацию универсального интерфейса <xref:System.Collections.Generic.IComparer%601> в качестве параметра.  
  
- Требуются ли быстрый поиск и получение данных?  
  
  - <xref:System.Collections.Specialized.ListDictionary> быстрее, чем <xref:System.Collections.Hashtable>, для небольших коллекций (10 элементов или меньше). Универсальный класс <xref:System.Collections.Generic.Dictionary%602> обеспечивает более быстрый поиск, чем универсальный класс <xref:System.Collections.Generic.SortedDictionary%602>. Многопоточной реализацией является <xref:System.Collections.Concurrent.ConcurrentDictionary%602>. <xref:System.Collections.Concurrent.ConcurrentBag%601> обеспечивает быструю многопоточную вставку для неупорядоченных данных. Дополнительные сведения об обоих многопоточных типах см. в разделе [Преимущества использования потокобезопасных коллекций](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).  
  
- Требуются ли вам коллекции, принимающие только строки?  
  
  - Классы <xref:System.Collections.Specialized.StringCollection> (на основе <xref:System.Collections.IList>) и <xref:System.Collections.Specialized.StringDictionary> (на основе <xref:System.Collections.IDictionary>) находятся в пространстве имен <xref:System.Collections.Specialized>.  
  
  - Кроме того, можно использовать любой из универсальных классов коллекций в пространстве имен <xref:System.Collections.Generic> как строго типизированную строковую коллекцию, указав класс <xref:System.String> в качестве аргумента универсального типа. Например, можно объявить переменную с типом [List\<String>](xref:System.Collections.Generic.List%601) или [Dictionary<String,String>](xref:System.Collections.Generic.Dictionary%602).
  
## <a name="linq-to-objects-and-plinq"></a>LINQ to Objects и PLINQ  
 Язык LINQ to Objects позволяет использовать запросы LINQ для доступа к объектам в памяти при условии, что тип объекта реализует интерфейс <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601>. Запросы LINQ обеспечивают общий шаблон для доступа к данным, обычно являются более четкими и удобочитаемыми, чем стандартные циклы `foreach`, а также предоставляют возможности фильтрации, сортировки и группировки. Дополнительные сведения см. в разделах [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md) и [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md).  
  
 Язык PLINQ предоставляет параллельную реализацию языка LINQ to Objects, которая может обеспечить более быстрое выполнение запросов во многих сценариях за счет более эффективного использования многоядерных компьютеров. Дополнительные сведения см. в разделе [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Collections>
- <xref:System.Collections.Specialized>
- <xref:System.Collections.Generic>
- [Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md)
