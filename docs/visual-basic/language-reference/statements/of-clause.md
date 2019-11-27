---
title: Предложение Of
ms.date: 07/20/2015
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
ms.openlocfilehash: d88c43efe858d6b81b7d8d2470b234ff5d40632a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353843"
---
# <a name="of-clause-visual-basic"></a>Предложение Of (Visual Basic)
Вводит предложение `Of`, которое определяет *параметр типа* в *универсальном* классе, структуре, интерфейсе, делегате или процедуре. Сведения об универсальных типах см. [в разделе Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Использование ключевого слова of  
 В следующем примере кода ключевое слово `Of` используется для определения структуры класса, принимающего два параметра типа. Он *ограничивает* параметр `keyType` интерфейсом <xref:System.IComparable>, что означает, что в используемом коде должен быть указан аргумент типа, реализующий <xref:System.IComparable>. Это необходимо для того, чтобы процедура `add` могла вызвать метод <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType>. Дополнительные сведения об ограничениях см. в разделе [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
```vb  
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
  
 Если вы закончите предыдущее определение класса, можно создать из него разнообразные `dictionary` классы. Типы, предоставляемые для `entryType` и `keyType` определяют, какой тип записи принадлежит классу и какой тип ключа он связывает с каждой записью. Из-за ограничения необходимо указать, чтобы `keyType` тип, реализующий <xref:System.IComparable>.  
  
 В следующем примере кода создается объект, содержащий `String` записи и связывающий ключ `Integer` с каждым из них. `Integer` реализует <xref:System.IComparable> и, следовательно, удовлетворяет ограничениям на `keyType`.  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 Ключевое слово `Of` можно использовать в следующих контекстах:  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также:

- <xref:System.IComparable>
- [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
