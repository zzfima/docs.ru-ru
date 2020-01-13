---
title: Универсальные коллекции в .NET
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET], collections
- generic collections [.NET]
- generic types [.NET]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
ms.openlocfilehash: dce0e38b0198396ec0dbc3ced7f2f59c2b112b56
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708414"
---
# <a name="generic-collections-in-net"></a>Универсальные коллекции в .NET

 Библиотека классов .NET предоставляет ряд универсальных классов коллекций в пространствах имен <xref:System.Collections.Generic> и <xref:System.Collections.ObjectModel>. См. дополнительные сведения о [часто используемых типах коллекций](../../../docs/standard/collections/commonly-used-collection-types.md).  
  
## <a name="systemcollectionsgeneric"></a>System.Collections.Generic

 Многие универсальные типы коллекций являются прямыми аналогами неуниверсальных типов. Интерфейс <xref:System.Collections.Generic.Dictionary%602> — это универсальная версия <xref:System.Collections.Hashtable>; он использует для перечисления универсальную структуру <xref:System.Collections.Generic.KeyValuePair%602> вместо <xref:System.Collections.DictionaryEntry>.  
  
 <xref:System.Collections.Generic.List%601> — это универсальная версия <xref:System.Collections.ArrayList>. Имеются универсальные классы <xref:System.Collections.Generic.Queue%601> и <xref:System.Collections.Generic.Stack%601>, соответствующие неуниверсальным версиям.  
  
 Существуют универсальные и неуниверсальные версии <xref:System.Collections.Generic.SortedList%602>. Обе эти версии являются гибридами словаря и списка. Универсальный класс <xref:System.Collections.Generic.SortedDictionary%602> представляет собой обычный словарь и не имеет неуниверсального аналога.  
  
 Универсальный класс <xref:System.Collections.Generic.LinkedList%601> является истинным связанным списком. У него нет неуниверсального аналога.  
  
## <a name="systemcollectionsobjectmodel"></a>System.Collections.ObjectModel

 Универсальный класс <xref:System.Collections.ObjectModel.Collection%601> предоставляет базовый класс для создания собственных производных универсальных типов коллекций. Класс <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> позволяет легко создавать доступные только для чтения коллекции на основе любого типа, реализующего универсальный интерфейс <xref:System.Collections.Generic.IList%601>. Универсальный класс <xref:System.Collections.ObjectModel.KeyedCollection%602> предоставляет способ хранения объектов, содержащих свои собственные ключи.  
  
## <a name="other-generic-types"></a>Прочие универсальные типы

 Универсальная структура <xref:System.Nullable%601> позволяет использовать типы значений так, как будто им могут быть присвоены значения `null`. Это может быть полезно при работе с запросами к базе данных, где поля, содержащие типы значений, могут опускаться. Параметр универсального типа может принимать значения любого типа.  
  
> [!NOTE]
> В C# и Visual Basic нет необходимости явно использовать <xref:System.Nullable%601>, так как язык имеет синтаксис для типов, допускающий значение null. См. статьи о типах значений, допускающих значение NULL, [для C#](../../csharp/language-reference/builtin-types/nullable-value-types.md) и [Visual Basic](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).
  
 Универсальная структура <xref:System.ArraySegment%601> предоставляет способ выделения диапазона элементов в одномерном массиве любого типа, начинающемся с нуля. Параметр универсального типа является типом элементов массива.  
  
 Универсальный делегат <xref:System.EventHandler%601> избавляет от необходимости объявления типа делегата для обработки событий, если такое событие соответствует шаблону обработки событий, используемому .NET Framework. Предположим, что вы создали класс `MyEventArgs`, производный от <xref:System.EventArgs>, для хранения данных события. Затем вы можете объявить событие следующим образом:  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [Универсальные шаблоны](../../../docs/standard/generics/index.md)
- [Универсальные методы-делегаты для управления массивами и списками](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)
- [Универсальные интерфейсы](../../../docs/standard/generics/interfaces.md)
