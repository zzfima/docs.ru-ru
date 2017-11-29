---
title: "Предложение Of (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ef3ac4ac88727b1dcae50fa14abde03f29a16fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="of-clause-visual-basic"></a>Предложение Of (Visual Basic)
Представляет `Of` предложение, которое идентифицирует *параметр типа* на *универсального* класса, структуры, интерфейса, делегата или процедуры. Сведения об универсальных типах см. в разделе [универсальных типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>С помощью ключевого слова  
 Следующий пример кода использует `Of` ключевое слово, чтобы определить структуру класса, который принимает два параметра типа. Он *ограничивает* `keyType` по <xref:System.IComparable> интерфейс, который означает код-потребитель необходимо указать аргумент типа, который реализует <xref:System.IComparable>. Это необходимо, чтобы `add` процедура может вызывать <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> метод. Дополнительные сведения об ограничениях см. в разделе [список типов](../../../visual-basic/language-reference/statements/type-list.md).  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 Если выполнить предыдущий определение класса, можно создать различные `dictionary` классы из него. Типы, которые вводятся `entryType` и `keyType` определить класс содержит тип и тип ключа, связываемого с каждой записи. Из-за ограничений, необходимо указать `keyType` тип, реализующий <xref:System.IComparable>.  
  
 В следующем примере кода создается объект, который содержит `String` записей и связывает `Integer` ключа с каждой из них. `Integer`реализует <xref:System.IComparable> и поэтому удовлетворяет ограничению на `keyType`.  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 Ключевое слово `Of` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 <xref:System.IComparable>  
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
