---
title: "Практическое руководство. Определение наличия связи между двумя объектами (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "наследование, объекты Visual Basic"
  - "объектные переменные, определение отношений"
  - "объекты [Visual Basic], наследование"
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Практическое руководство. Определение наличия связи между двумя объектами (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Сравнивая два объекта можно определить взаимосвязь, если она есть, между классами, от которых они произошли.  Метод <xref:System.Type.IsInstanceOfType%2A> класса <xref:System.Type?displayProperty=fullName> возвращает значение `True`, если указанный класс наследует от данного класса или если данный тип является интерфейсом, поддерживаемым указанным классом.  
  
### Определить наследует ли объект от класса или интерфейса другого объекта  
  
1.  У объекта, тип которого может быть базовым типом, вызовите метод <xref:System.Object.GetType%2A>.  
  
2.  У объекта <xref:System.Type?displayProperty=fullName>, который был получен вызовом <xref:System.Object.GetType%2A>, вызовите метод <xref:System.Type.IsInstanceOfType%2A>.  
  
3.  В списке аргументов для <xref:System.Type.IsInstanceOfType%2A> укажите объект, тип которого проверяется, не является ли он производным типом.  
  
     <xref:System.Type.IsInstanceOfType%2A> возвращает `True`, если тип аргумента наследует от типа объекта <xref:System.Type?displayProperty=fullName>.  
  
## Пример  
 В следующем примере определяется, является ли класс одного объекта производным от класса другого объекта:  
  
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
  
 Заметьте, что при вызове метода <xref:System.Type.IsInstanceOfType%2A> задаются две переменные объекта.  Предполагаемый базовый тип используется для создания класса <xref:System.Type?displayProperty=fullName>, а предполагаемый производный тип передается как аргумент в метод <xref:System.Type.IsInstanceOfType%2A>.  
  
## См. также  
 <xref:System.Object.GetType%2A>   
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Type.IsInstanceOfType%2A>   
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Практическое руководство. Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)