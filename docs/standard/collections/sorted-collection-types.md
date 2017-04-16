---
title: "Отсортированные типы коллекций | Microsoft Docs"
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
  - "коллекции [платформа .NET Framework], SortedList - тип коллекции"
  - "группировка данных в коллекциях, SortedList - тип коллекции"
  - "SortedDictionary - тип коллекции"
  - "SortedList - класс, группировка данных в коллекциях"
  - "SortedList - тип коллекции"
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Отсортированные типы коллекций
Класс <xref:System.Collections.SortedList?displayProperty=fullName>, универсальные классы <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> и <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> подобны классу <xref:System.Collections.Hashtable> и универсальному классу <xref:System.Collections.Generic.Dictionary%602> в том, что реализуют интерфейс <xref:System.Collections.IDictionary>, но поддерживают их элементы в порядке сортировки по ключу и не имеют характеристики вставки и извлечения O\(1\) хэш\-таблиц.  Эти три класса имеют некоторые общие возможности:  
  
-   Все три класса реализуют интерфейс <xref:System.Collections.IDictionary?displayProperty=fullName>.  Два универсальных класса также реализуют универсальный интерфейс <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>.  
  
-   Каждый элемент представляет собой пару ключ\/значение для осуществления перечисления.  
  
    > [!NOTE]
    >  При перечислении неуниверсальный класс <xref:System.Collections.SortedList> возвращает объекты <xref:System.Collections.DictionaryEntry>, но оба универсальных типа возвращают объекты <xref:System.Collections.Generic.KeyValuePair%602>.  
  
-   Элементы сортируются согласно реализации <xref:System.Collections.IComparer?displayProperty=fullName> \(для неуниверсального класса <xref:System.Collections.SortedList>\) или реализации <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> \(для обоих универсальных классов\).  
  
-   Каждый класс предоставляет свойства, которые возвращают коллекции, содержащие только ключи или только значения.  
  
 В следующей таблице перечислены некоторые различия между двумя классами отсортированных списков и классом <xref:System.Collections.Generic.SortedDictionary%602>.  
  
|Неуниверсальный класс <xref:System.Collections.SortedList> и универсальный класс <xref:System.Collections.Generic.SortedList%602>|Универсальный класс <xref:System.Collections.Generic.SortedDictionary%602>|  
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|Свойства, возвращающие ключи и значения, индексируются, позволяя производить эффективное индексированное извлечение.|Неиндексированное извлечение.|  
|Извлечение O\(log `n`\).|Извлечение O\(log `n`\).|  
|Вставка и удаление, как правило, являются O\(`n`\); однако, для данных, которые уже упорядочены, вставка является O\(1\), поэтому каждый элемент будет добавляться в конец списка. \(Предполагается, что изменение размера не требуется.\)|Вставка и удаление являются O\(log `n`\).|  
|Использует меньше памяти, чем <xref:System.Collections.Generic.SortedDictionary%602>.|Использует больше памяти, чем неуниверсальный класс <xref:System.Collections.SortedList> и универсальный класс <xref:System.Collections.Generic.SortedList%602>.|  
  
 Для упорядоченных списков или словарей, которые должны быть одновременно доступны при обращении из нескольких потоков, можно добавить логику сортировки в класс, производный от <xref:System.Collections.Concurrent.ConcurrentDictionary%602>.  
  
> [!NOTE]
>  Для значений, содержащих собственные ключи \(например, запись о сотруднике, в которой содержится идентификатор сотрудника\), можно создать коллекцию с ключом, имеющую некоторые характеристики списка и некоторые характеристики словаря, путем наследования от универсального класса <xref:System.Collections.ObjectModel.KeyedCollection%602>.  
  
 Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], класс <xref:System.Collections.Generic.SortedSet%601> предоставляет самобалансирующееся дерево, которое поддерживает данные в отсортированном порядке после операций вставки, удаления и поиска.  Этот класс и класс <xref:System.Collections.Generic.HashSet%601> реализуют интерфейс <xref:System.Collections.Generic.ISet%601>.  
  
## См. также  
 <xref:System.Collections.IDictionary?displayProperty=fullName>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>   
 [Часто используемые типы коллекций](../../../docs/standard/collections/commonly-used-collection-types.md)