---
title: Когда следует использовать универсальные коллекции
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- collections [.NET Framework], generic
- generic collections [.NET Framework]
ms.assetid: e7b868b1-11fe-4ac5-bed3-de68aca47739
ms.openlocfilehash: 7d59259c1cab6842ef62888bf5326225394d8d44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711211"
---
# <a name="when-to-use-generic-collections"></a>Когда следует использовать универсальные коллекции
Использование универсальных коллекций является рекомендуемой практикой, поскольку при этом сразу же обеспечивается безопасность типов без необходимости наследования от базового типа коллекции и реализации элементов определенного типа. Типы универсальных коллекций обычно работают лучше, чем соответствующие типы неуниверсальных коллекций (и лучше, чем типы, являющиеся производными от базовых типов неуниверсальных коллекций), если элементами коллекции являются типы значений, поскольку при использовании универсальных коллекций упаковывать элементы не требуется.  
  
 В программах, предназначенных для .NET Framework 4 или более поздней версии, следует использовать универсальные классы-коллекции из пространства имен <xref:System.Collections.Concurrent>, если несколько потоков могут одновременно добавлять и (или) удалять элементы коллекции.  
  
 Следующие универсальные типы соответствуют существующим типам коллекций.  
  
- <xref:System.Collections.Generic.List%601> — это универсальный класс, соответствующий <xref:System.Collections.ArrayList>.  
  
- <xref:System.Collections.Generic.Dictionary%602> и <xref:System.Collections.Concurrent.ConcurrentDictionary%602> — универсальные классы, соответствующие <xref:System.Collections.Hashtable>.  
  
- <xref:System.Collections.ObjectModel.Collection%601> — это универсальный класс, соответствующий <xref:System.Collections.CollectionBase>. <xref:System.Collections.ObjectModel.Collection%601> может использоваться как базовый класс, но в отличие от <xref:System.Collections.CollectionBase> он не является абстрактным. Это значительно упрощает его использование.  
  
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> — это универсальный класс, соответствующий <xref:System.Collections.ReadOnlyCollectionBase>. <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> не является абстрактным и имеет конструктор, упрощающий представление существующего класса <xref:System.Collections.Generic.List%601> в виде коллекции только для чтения.  
  
- Универсальные классы <xref:System.Collections.Generic.Queue%601>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Generic.Stack%601>, <xref:System.Collections.Concurrent.ConcurrentStack%601>и <xref:System.Collections.Generic.SortedList%602> соответствуют аналогичным неуниверсальным классам с теми же именами.  
  
## <a name="additional-types"></a>Дополнительные типы  
 Несколько типов универсальных коллекций не имеют неуниверсальных аналогов. К ним относятся следующие:  
  
- <xref:System.Collections.Generic.LinkedList%601> является связанным списком общего назначения, обеспечивающий выполнение операций вставки и удаления O(1).  
  
- <xref:System.Collections.Generic.SortedDictionary%602> — это сортируемый словарь с O(log `n`) операциями вставки и извлечения, что делает его полезной альтернативой для <xref:System.Collections.Generic.SortedList%602>.  
  
- <xref:System.Collections.ObjectModel.KeyedCollection%602> — это гибрид списка и словаря, который предоставляет способ хранения объектов, содержащих свои собственные ключи.  
  
- <xref:System.Collections.Concurrent.BlockingCollection%601> реализует класс коллекции с функциями границы и блокировки.  
  
- <xref:System.Collections.Concurrent.ConcurrentBag%601> предоставляет возможности быстрой вставки и удаления неупорядоченных элементов.  
  
## <a name="linq-to-objects"></a>LINQ to Objects  
 Функция LINQ to Objects позволяет использовать запросы LINQ для доступа к объектам в памяти при условии, что тип объекта реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> . LINQ запросы предоставляют общий шаблон для доступа к данным, являются более четкими и удобочитаемыми, чем стандартные циклы `foreach`, а также предоставляют возможности фильтрации, сортировки и группировки. LINQ запросы также могут повысить производительность. Дополнительные сведения см. в разделах [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) и [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="additional-functionality"></a>Дополнительные функциональные возможности  
 Некоторые универсальные типы имеют функциональные возможности, отсутствующие в неуниверсальных коллекциях. Например, класс <xref:System.Collections.Generic.List%601> , который соответствует неуниверсальный классу <xref:System.Collections.ArrayList> , имеет ряд методов, которые принимают универсальные делегаты, такие как делегат <xref:System.Predicate%601> , который позволяет указать методы для поиска в списке, делегат <xref:System.Action%601> , который представляет методы, выполняемые с каждым элементом списка, и делегат <xref:System.Converter%602> , который позволяет определять преобразования между типами.  
  
 Класс <xref:System.Collections.Generic.List%601> позволяет задавать свои собственные реализации универсального интерфейса <xref:System.Collections.Generic.IComparer%601> для сортировки и поиска в списке. Классы <xref:System.Collections.Generic.SortedDictionary%602> и <xref:System.Collections.Generic.SortedList%602> также имеют эту возможность. Кроме того эти классы позволяют задавать функции сравнения при создании коллекции. Аналогично, классы <xref:System.Collections.Generic.Dictionary%602> и <xref:System.Collections.ObjectModel.KeyedCollection%602> позволяют задавать собственные сравнения на равенство.  
  
## <a name="see-also"></a>См. также раздел

- [Коллекции и структуры данных](../../../docs/standard/collections/index.md)
- [Часто используемые типы коллекций](../../../docs/standard/collections/commonly-used-collection-types.md)
- [Универсальные шаблоны](../../../docs/standard/generics/index.md)
