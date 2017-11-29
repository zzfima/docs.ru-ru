---
title: "Практическое руководство. Определение наличия связи между двумя объектами (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7824742459fca355c0043ad8ed20a26330402c05
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Практическое руководство. Определение наличия связи между двумя объектами (Visual Basic)
Можно сравнить два объекта, чтобы определить связь между классами, от которых они создаются. <xref:System.Type.IsInstanceOfType%2A> Метод <xref:System.Type?displayProperty=nameWithType> возвращает `True` Если класс наследуется от текущего класса или если текущий тип является интерфейсом, который поддерживается с помощью указанного класса.  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Чтобы определить, если один объект наследует от класса или интерфейса другого объекта  
  
1.  В объекте, который вы считаете, может быть базового типа, вызывают <xref:System.Object.GetType%2A> метод.  
  
2.  На <xref:System.Type?displayProperty=nameWithType> объект, возвращаемый <xref:System.Object.GetType%2A>, вызвать <xref:System.Type.IsInstanceOfType%2A> метод.  
  
3.  В списке аргументов для <xref:System.Type.IsInstanceOfType%2A>, укажите объект, вы считаете, может быть производного типа.  
  
     <xref:System.Type.IsInstanceOfType%2A>Возвращает `True` Если тип аргумента наследует от <xref:System.Type?displayProperty=nameWithType> тип объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется, является ли один объект представляет класс, производный от класса другого объекта.  
  
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
  
 Заметьте, переменные два объекта в вызове <xref:System.Type.IsInstanceOfType%2A>. Предполагаемый базовый тип используется для создания <xref:System.Type?displayProperty=nameWithType> класс и предполагаемый производный тип передается в качестве аргумента для <xref:System.Type.IsInstanceOfType%2A> метод.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.IsInstanceOfType%2A>  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Практическое руководство. Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
