---
title: Отсортированные типы коллекций
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- SortedDictionary collection type
- SortedList class, grouping data in collections
- grouping data in collections, SortedList collection type
- SortedList collection type
- collections [.NET Framework], SortedList collection type
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
ms.openlocfilehash: adabda4801abc7a11a9b22181701eb233b35a251
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711341"
---
# <a name="sorted-collection-types"></a>Отсортированные типы коллекций
Класс <xref:System.Collections.SortedList?displayProperty=nameWithType>, универсальный класс <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> и универсальный класс <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> похожи на класс <xref:System.Collections.Hashtable> и универсальный класс <xref:System.Collections.Generic.Dictionary%602> в том, что они реализуют интерфейс <xref:System.Collections.IDictionary>, но сортировка элементов в них осуществляется по ключу. Кроме того, в них отсутствует возможность вставки O(1) и извлечения характеристик хэш-таблиц. Эти три класса имеют ряд схожих свойств:  
  
- Все три класса реализуют интерфейс <xref:System.Collections.IDictionary?displayProperty=nameWithType>. Два универсальных класса также реализуют универсальный интерфейс <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>.  
  
- Каждый элемент является парой ключ-значение для перечисления.  
  
    > [!NOTE]
    > Неуниверсальный класс <xref:System.Collections.SortedList> возвращает при перечислении объекты <xref:System.Collections.DictionaryEntry>, несмотря на то, что два универсальных типа возвращают объекты <xref:System.Collections.Generic.KeyValuePair%602>.  
  
- Элементы сортируются в соответствии с реализацией <xref:System.Collections.IComparer?displayProperty=nameWithType> (для неуниверсального класса <xref:System.Collections.SortedList>) или с реализацией <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> (для двух универсальных классов).  
  
- Каждый класс предоставляет свойства, которые возвращают коллекции, содержащие только ключи или только значения.  
  
 В таблице ниже перечислены некоторые отличия между двумя классами отсортированных списков и классом <xref:System.Collections.Generic.SortedDictionary%602>.  
  
|Неуниверсальный класс <xref:System.Collections.SortedList> и универсальный класс <xref:System.Collections.Generic.SortedList%602>.|Универсальный класс <xref:System.Collections.Generic.SortedDictionary%602>.|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|Свойства, возвращающие ключи и значения, индексируются, что позволяет выполнять эффективное индексированное извлечение.|Неиндексированное извлечение.|  
|Извлечение — O(log `n`).|Извлечение — O(log `n`).|  
|Вставка и удаление, как правило, являются O(`n`), но вставка является O(log `n`) для данных, которые уже отсортированы, чтобы каждый элемент добавлялся в конец списка. (Предполагается, что изменение размера не требуется.)|Вставка и удаление являются O(log `n`).|  
|Использует меньше памяти, чем <xref:System.Collections.Generic.SortedDictionary%602>.|Использует больше памяти, чем неуниверсальный класс <xref:System.Collections.SortedList> и универсальный класс <xref:System.Collections.Generic.SortedList%602>.|  
  
 Для отсортированных списков или словарей, которые должны быть доступны одновременно из множества потоков, вы можете добавить в производный класс от <xref:System.Collections.Concurrent.ConcurrentDictionary%602> логику сортировки.  
  
> [!NOTE]
> Для значений, содержащих собственные ключи (например, записи о сотрудниках, содержащие идентификационный номер сотрудника), вы можете создать коллекцию с ключами, имеющую некоторые характеристики списка и некоторые характеристики словаря. Для этого необходимо создать производный класс от универсального класса <xref:System.Collections.ObjectModel.KeyedCollection%602>.  
  
 Начиная с .NET Framework 4, класс <xref:System.Collections.Generic.SortedSet%601> предоставляет самобалансируемое дерево, в котором после операций вставки, удаления или поиска данные сохраняются в отсортированном порядке. Этот класс и класс <xref:System.Collections.Generic.HashSet%601> реализуют интерфейс <xref:System.Collections.Generic.ISet%601>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.IDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.ConcurrentDictionary%602>
- [Часто используемые типы коллекций](../../../docs/standard/collections/commonly-used-collection-types.md)
