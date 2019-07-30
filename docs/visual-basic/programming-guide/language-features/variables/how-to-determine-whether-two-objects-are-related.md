---
title: Практическое руководство. Определить, связаны ли два объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2b17be4ef5a7dabfc4779ab6f5675cc2baec9c3c
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626555"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Практическое руководство. Определить, связаны ли два объекта (Visual Basic)

Можно сравнить два объекта, чтобы определить связь между классами, из которых они были созданы. <xref:System.Type.IsInstanceOfType%2A> Метод класса<xref:System.Type?displayProperty=nameWithType> возвращает значение,еслиуказанныйкласснаследуетсяоттекущегокласса,илиеслитекущийтипявляетсяинтерфейсом`True` , поддерживаемым указанным классом.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Определение того, наследуется ли один объект от класса или интерфейса другого объекта

1. В объекте, который вы считаете, может быть базовым типом, вызовите <xref:System.Object.GetType%2A> метод.

2. В объекте, возвращенном <xref:System.Object.GetType%2A>методом, вызовите <xref:System.Type.IsInstanceOfType%2A> метод. <xref:System.Type?displayProperty=nameWithType>

3. В списке аргументов для <xref:System.Type.IsInstanceOfType%2A>укажите объект, который может иметь производный тип.

    <xref:System.Type.IsInstanceOfType%2A>Возвращает `True` значение, <xref:System.Type?displayProperty=nameWithType> если тип его аргумента наследуется от типа объекта.

## <a name="example"></a>Пример
 В следующем примере определяется, представляет ли один объект класс, производный от класса другого объекта.

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

Обратите внимание на непредвиденное размещение двух переменных объекта в вызове <xref:System.Type.IsInstanceOfType%2A>. Предполагаемый базовый тип используется для создания <xref:System.Type?displayProperty=nameWithType> класса, а предполагаемый производный тип передается в качестве аргумента <xref:System.Type.IsInstanceOfType%2A> в метод.

## <a name="see-also"></a>См. также

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Практическое руководство. Определить, идентичны ли два объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
