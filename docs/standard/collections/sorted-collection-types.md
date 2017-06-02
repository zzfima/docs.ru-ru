---
title: "Отсортированные типы коллекций | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SortedDictionary collection type
- SortedList class, grouping data in collections
- grouping data in collections, SortedList collection type
- SortedList collection type
- collections [.NET Framework], SortedList collection type
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2ac1552dba8756d033ee02651142476c4a15a485
ms.lasthandoff: 04/18/2017

---
# <a name="sorted-collection-types"></a>Отсортированные типы коллекций
Класс <xref:System.Collections.SortedList?displayProperty=fullName>, универсальный класс <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> и универсальный класс <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> схожи с классом <xref:System.Collections.Hashtable> и универсальным классом <xref:System.Collections.Generic.Dictionary%602> в том, что реализуют интерфейс <xref:System.Collections.IDictionary>, однако сортировку своих элементов они выполняют по ключам. Кроме того, в них отсутствуют функции вставки O(1) и извлечения характеристик хэш-таблиц. Эти три класса имеют ряд схожих свойств:  
  
-   Все три класса реализуют интерфейс <xref:System.Collections.IDictionary?displayProperty=fullName>. Два универсальных класса также реализуют универсальный интерфейс <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>.  
  
-   Каждый элемент является парой ключ-значение для перечисления.  
  
    > [!NOTE]
    >  Неуниверсальный класс <xref:System.Collections.SortedList> возвращает объекты <xref:System.Collections.DictionaryEntry> при перечислении, несмотря на то что два универсальных типа возвращают объекты <xref:System.Collections.Generic.KeyValuePair%602>.  
  
-   Элементы сортируются в соответствии с реализацией <xref:System.Collections.IComparer?displayProperty=fullName> (для неуниверсального <xref:System.Collections.SortedList>) или реализацией <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> (для двух универсальных классов).  
  
-   Каждый класс предоставляет свойства, которые возвращают коллекции, содержащие только ключи или только значения.  
  
 В таблице ниже перечислены некоторые различия между двумя классами отсортированных списков и классом <xref:System.Collections.Generic.SortedDictionary%602>.  
  
|Неуниверсальный класс <xref:System.Collections.SortedList> и универсальный класс <xref:System.Collections.Generic.SortedList%602>|Универсальный класс <xref:System.Collections.Generic.SortedDictionary%602>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|Свойства, возвращающие ключи и значения, индексируются, что позволяет выполнять эффективное индексированное извлечение.|Неиндексированное извлечение.|  
|Извлечение — O(log `n`).|Извлечение — O(log `n`).|  
|Вставка и удаление, как правило, являются O(`n`); тем не менее вставка является O(1) для данных, которые уже отсортированы, чтобы каждый элемент добавлялся в конец списка. (Предполагается, что изменение размера не требуется.)|Вставка и удаление являются O(log `n`).|  
|Использует меньше памяти, чем <xref:System.Collections.Generic.SortedDictionary%602>.|Использует больше памяти, чем неуниверсальный класс <xref:System.Collections.SortedList> и универсальный класс <xref:System.Collections.Generic.SortedList%602>.|  
  
 Для отсортированных списков или словарей, которые должны быть доступны одновременно из нескольких потоков, можно добавить логику сортировки в класс, производный от класса <xref:System.Collections.Concurrent.ConcurrentDictionary%602>.  
  
> [!NOTE]
>  Для значений, содержащих собственные ключи (например, записи о сотрудниках, содержащие идентификатор сотрудника), можно создать коллекцию с ключом, имеющую некоторые характеристики списка и словаря, путем создания класса, производного от универсального класса <xref:System.Collections.ObjectModel.KeyedCollection%602>.  
  
 Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] класс <xref:System.Collections.Generic.SortedSet%601> предоставляет самобалансируемое дерево, в котором данные хранятся в отсортированном порядке после операций вставки, удаления и поиска. Этот класс и класс <xref:System.Collections.Generic.HashSet%601> реализуют интерфейс <xref:System.Collections.Generic.ISet%601>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.IDictionary?displayProperty=fullName>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>   
 [Часто используемые типы коллекций](../../../docs/standard/collections/commonly-used-collection-types.md)
