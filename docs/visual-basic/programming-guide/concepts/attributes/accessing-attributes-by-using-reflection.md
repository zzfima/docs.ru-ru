---
title: "Доступ к атрибутам с помощью отражения (Visual Basic) | Документы Microsoft"
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
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
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
ms.openlocfilehash: 4763eccc5d1a6bdf3e89c1c4d825d5ff5c6caa3e
ms.lasthandoff: 03/13/2017

---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a>Доступ к атрибутам с помощью отражения (Visual Basic)
Тот факт, что можно определять настраиваемые атрибуты и поместить их в исходный код будет мало пользы, без какой-либо способ извлечения этих сведений и работы с ними. С помощью отражения, можно получить информацию, которая была определена с настраиваемыми атрибутами. Основной метод — `GetCustomAttributes`, который возвращает массив объектов, которые являются эквивалентами времени выполнения атрибутов исходного кода. Этот метод имеет несколько перегруженных версий. Дополнительные сведения см. в разделе <xref:System.Attribute>.</xref:System.Attribute>  
  
 Спецификация атрибута, например:  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 эквивалентен концептуально это:  
  
```vb  
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")  
anonymousAuthorObject.version = 1.1  
```  
  
 Тем не менее, код не выполняется до `SampleClass` запрос по атрибутам. Вызов `GetCustomAttributes` на `SampleClass` вызывает `Author` объект создается и инициализируется как описано выше. Если класс имеет другие атрибуты, другие объекты атрибута создаются аналогично. `GetCustomAttributes`Возвращает `Author` объектом и другими объектами атрибута в массив. Затем можно перейти по этому массиву, определить, какие атрибуты были применены на основе типа элемента массива и извлечь сведения из объектов.  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример. Настраиваемый атрибут определен, применяется к нескольким сущностям и извлекается через отражение.  
  
```vb  
' Multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
  
        ' Default value  
        version = 1.0  
    End Sub  
  
    Function GetName() As String  
        Return name  
    End Function          
End Class  
  
' Class with the Author attribute  
<Author("P. Ackerman")>   
Public Class FirstClass  
End Class  
  
' Class without the Author attribute  
Public Class SecondClass  
End Class  
  
' Class with multiple Author attributes.  
<Author("P. Ackerman"), Author("R. Koch", Version:=2.0)>   
Public Class ThirdClass  
End Class  
  
Class TestAuthorAttribute  
    Sub Main()  
        PrintAuthorInfo(GetType(FirstClass))  
        PrintAuthorInfo(GetType(SecondClass))  
        PrintAuthorInfo(GetType(ThirdClass))  
    End Sub  
  
    Private Shared Sub PrintAuthorInfo(ByVal t As System.Type)  
        System.Console.WriteLine("Author information for {0}", t)  
  
        ' Using reflection  
        Dim attrs() As System.Attribute = System.Attribute.GetCustomAttributes(t)  
  
        ' Displaying output  
        For Each attr In attrs  
            Dim a As Author = CType(attr, Author)  
            System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version)  
        Next              
    End Sub  
  
    ' Output:  
    '   Author information for FirstClass  
    '     P. Ackerman, version 1.00  
    ' Author information for SecondClass  
    ' Author information for ThirdClass  
    '  R. Koch, version 2.00  
    '  P. Ackerman, version 1.00  
  
End Class  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Извлечение информации, сохраненной в атрибуте](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)   
 [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Создание настраиваемых атрибутов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
