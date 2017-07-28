---
title: "Универсальные коллекции в .NET Framework | Microsoft Docs"
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
  - "универсальные коллекции [платформа .NET Framework]"
  - "универсальные шаблоны [платформа .NET Framework], коллекции"
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Универсальные коллекции в .NET Framework
В этом разделе приводится обзор универсальных классов коллекций и других универсальных типов в составе платформы .NET Framework.  
  
## Универсальные коллекции в .NET Framework  
 Библиотека классов .NET Framework предоставляет ряд универсальных классов коллекций в пространствах имен <xref:System.Collections.Generic> и <xref:System.Collections.ObjectModel>.  Подробнее об этих классах см. в разделе [Часто используемые типы коллекций](../../../docs/standard/collections/commonly-used-collection-types.md).  
  
### System.Collections.Generic  
 Многие универсальные типы коллекций являются прямыми аналогами неуниверсальных типов.  Интерфейс <xref:System.Collections.Generic.Dictionary%602> — это универсальная версия <xref:System.Collections.Hashtable>; он использует для перечисления универсальную структуру <xref:System.Collections.Generic.KeyValuePair%602> вместо <xref:System.Collections.DictionaryEntry>.  
  
 <xref:System.Collections.Generic.List%601> — это универсальная версия <xref:System.Collections.ArrayList>.  Имеются универсальные классы <xref:System.Collections.Generic.Queue%601> и <xref:System.Collections.Generic.Stack%601>, соответствующие неуниверсальным версиям.  
  
 Существуют универсальные и неуниверсальные версии <xref:System.Collections.Generic.SortedList%602>.  Обе эти версии являются гибридами словаря и списка.  Универсальный класс <xref:System.Collections.Generic.SortedDictionary%602> представляет собой обычный словарь и не имеет неуниверсального аналога.  
  
 Универсальный класс <xref:System.Collections.Generic.LinkedList%601> является истинным связанным списком.  У него нет неуниверсального аналога.  
  
### System.Collections.ObjectModel  
 Универсальный класс <xref:System.Collections.ObjectModel.Collection%601> предоставляет базовый класс для создания собственных производных универсальных типов коллекций.  Класс <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> позволяет легко создавать доступные только для чтения коллекции на основе любого типа, реализующего универсальный интерфейс <xref:System.Collections.Generic.IList%601>.  Универсальный класс <xref:System.Collections.ObjectModel.KeyedCollection%602> предоставляет способ хранения объектов, содержащих свои собственные ключи.  
  
## Прочие универсальные типы  
 Универсальная структура <xref:System.Nullable%601> позволяет использовать типы значений так, как будто им могут быть присвоены значения `null`.  Это может быть полезно при работе с запросами к базе данных, где поля, содержащие типы значений, могут опускаться.  Параметр универсального типа может принимать значения любого типа.  
  
> [!NOTE]
>  В C\# нет необходимости явно использовать <xref:System.Nullable%601>, так как язык имеет синтаксис для типов, допускающих значение NULL.  
  
 Универсальная структура <xref:System.ArraySegment%601> предоставляет способ выделения диапазона элементов в одномерном массиве любого типа, начинающемся с нуля.  Параметр универсального типа является типом элементов массива.  
  
 Универсальный делегат <xref:System.EventHandler%601> избавляет от необходимости объявления типа делегата для обработки событий, если такое событие соответствует шаблону обработки событий, используемому [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  Предположим, что вы создали класс `MyEventArgs`, производный от <xref:System.EventArgs>, для хранения данных события.  Затем вы можете объявить событие следующим образом:  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## См. также  
 <xref:System.Collections.Generic?displayProperty=fullName>   
 <xref:System.Collections.ObjectModel?displayProperty=fullName>   
 [Универсальные шаблоны](../../../docs/standard/generics/index.md)   
 [Универсальные делегаты для управления массивами и списками](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)   
 [Универсальные интерфейсы](../../../docs/standard/generics/interfaces.md)