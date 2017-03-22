---
title: "Вариативность в универсальных интерфейсах (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c53c27bdb085213046553fc4b08f11336880a7c2
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-visual-basic"></a>Вариативность в универсальных интерфейсах (Visual Basic)
Платформа .NET framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов. Поддержка вариативности позволяет выполнять неявное преобразование классов, реализующих эти интерфейсы. Вариант теперь являются следующие интерфейсы:  
  
-   <xref:System.Collections.Generic.IEnumerable%601>(T является ковариантным)</xref:System.Collections.Generic.IEnumerable%601>  
  
-   <xref:System.Collections.Generic.IEnumerator%601>(T является ковариантным)</xref:System.Collections.Generic.IEnumerator%601>  
  
-   <xref:System.Linq.IQueryable%601>(T является ковариантным)</xref:System.Linq.IQueryable%601>  
  
-   <xref:System.Linq.IGrouping%602>(`TKey` и `TElement` ковариантных)</xref:System.Linq.IGrouping%602>  
  
-   <xref:System.Collections.Generic.IComparer%601>(T является контравариантным)</xref:System.Collections.Generic.IComparer%601>  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601>(T является контравариантным)</xref:System.Collections.Generic.IEqualityComparer%601>  
  
-   <xref:System.IComparable%601>(T является контравариантным)</xref:System.IComparable%601>  
  
 Ковариация позволяет методу иметь более производный тип возвращаемого значения, определенного параметром универсального типа интерфейса. Чтобы продемонстрировать функцию ковариации, рассмотрим следующие универсальные интерфейсы: `IEnumerable(Of Object)` и `IEnumerable(Of String)`. `IEnumerable(Of String)` Не наследует интерфейс `IEnumerable(Of Object)` интерфейс. Тем не менее `String` тип наследовать `Object` типа, а в некоторых случаях может потребоваться назначение объектов этих интерфейсов друг с другом. Это показано в следующем примере кода.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 В более ранних версиях платформы .NET Framework, этот код вызовет ошибку компиляции в Visual Basic с `Option Strict On`. Но теперь вы можете использовать `strings` вместо `objects`, как показано в предыдущем примере, поскольку <xref:System.Collections.Generic.IEnumerable%601>интерфейс является ковариантным.</xref:System.Collections.Generic.IEnumerable%601>  
  
 Контрвариантность позволяет методу иметь типы аргументов, для которых меньше, чем указано параметром универсального интерфейса. Чтобы продемонстрировать функцию контравариации, предположим, что вы создали `BaseComparer` класса для сравнения экземпляров `BaseClass` класса. Класс `BaseComparer` реализует интерфейс `IEqualityComparer(Of BaseClass)`. Поскольку <xref:System.Collections.Generic.IEqualityComparer%601>интерфейса теперь является контравариантным, можно использовать `BaseComparer` для сравнения экземпляров классов, наследующих `BaseClass` класса</xref:System.Collections.Generic.IEqualityComparer%601> Это показано в следующем примере кода.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Дополнительные примеры см. в разделе [Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).  
  
 Вариативность в универсальных интерфейсах поддерживается только для ссылочных типов. Типы значений не поддерживают вариативность. Например `IEnumerable(Of Integer)` не может быть неявно преобразован в `IEnumerable(Of Object)`, так как целочисленные типы представлены по типу значения.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Также важно помнить, что классов, реализующих вариантные интерфейсы являются инвариантными. Например несмотря на то что <xref:System.Collections.Generic.List%601>реализует ковариантный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, нельзя неявно преобразовать `List(Of Object)` для `List(Of String)`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.List%601> Это показано в следующем примере кода.  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a>См. также  
 [Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)   
 [Создание вариативных универсальных интерфейсов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)   
 [Универсальные интерфейсы](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf)   
 [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
