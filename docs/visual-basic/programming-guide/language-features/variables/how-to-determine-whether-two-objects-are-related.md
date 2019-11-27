---
title: Практическое руководство. Определение наличия связи между двумя объектами
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b3f5fc017166ba9cf28359db5de850c81b73bd69
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348626"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Практическое руководство. Определение наличия связи между двумя объектами (Visual Basic)

Можно сравнить два объекта, чтобы определить связь между классами, из которых они были созданы. Метод <xref:System.Type.IsInstanceOfType%2A> класса <xref:System.Type?displayProperty=nameWithType> возвращает `True`, если указанный класс наследуется от текущего класса, или если текущий тип является интерфейсом, поддерживаемым указанным классом.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Определение того, наследуется ли один объект от класса или интерфейса другого объекта

1. В объекте, который вы считаете, может быть базовым типом, вызовите метод <xref:System.Object.GetType%2A>.

2. В объекте <xref:System.Type?displayProperty=nameWithType>, возвращенном <xref:System.Object.GetType%2A>, вызовите метод <xref:System.Type.IsInstanceOfType%2A>.

3. В списке аргументов для <xref:System.Type.IsInstanceOfType%2A>укажите объект, который может быть производным типом.

    <xref:System.Type.IsInstanceOfType%2A> возвращает `True`, если его тип аргумента наследуется от типа объекта <xref:System.Type?displayProperty=nameWithType>.

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

Обратите внимание на неожиданное размещение двух переменных объекта в вызове метода <xref:System.Type.IsInstanceOfType%2A>. Предполагаемый базовый тип используется для создания класса <xref:System.Type?displayProperty=nameWithType>, а предполагаемый производный тип передается в качестве аргумента методу <xref:System.Type.IsInstanceOfType%2A>.

## <a name="see-also"></a>См. также

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Практическое руководство. Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
