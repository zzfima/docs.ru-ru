---
title: Практическое руководство. Определение связи между двумя объектами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: f59e00d80d28fc4bf24874d25b5c12643649c834
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342106"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Практическое руководство. Определение связи между двумя объектами (Visual Basic)
Вы можете сравнить два объекта для определения связи между классами, из которых они создаются. <xref:System.Type.IsInstanceOfType%2A> Метод <xref:System.Type?displayProperty=nameWithType> возвращает `True` Если класс наследует от текущего класса или если текущий тип является интерфейсом, поддерживаемым указанного класса.  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Чтобы определить, если один объект наследует от класса или интерфейса другого объекта  
  
1. В объекте, который вы считаете может быть базового типа, вызывают <xref:System.Object.GetType%2A> метод.  
  
2. На <xref:System.Type?displayProperty=nameWithType> объект, возвращаемый <xref:System.Object.GetType%2A>, вызвать <xref:System.Type.IsInstanceOfType%2A> метод.  
  
3. В списке аргументов для <xref:System.Type.IsInstanceOfType%2A>, укажите объект, вы думаете, может быть производного типа.  
  
     <xref:System.Type.IsInstanceOfType%2A> Возвращает `True` Если тип аргумента наследует из <xref:System.Type?displayProperty=nameWithType> тип объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется, представляет ли один объект класса, производного от класса другого объекта.  
  
```  
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
  
 Заметьте, переменные два объекта в вызове <xref:System.Type.IsInstanceOfType%2A>. Предполагаемый базовый тип используется для создания <xref:System.Type?displayProperty=nameWithType> класс и предполагаемый производный тип передается в качестве аргумента <xref:System.Type.IsInstanceOfType%2A> метод.  
  
## <a name="see-also"></a>См. также

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Практическое руководство. Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
