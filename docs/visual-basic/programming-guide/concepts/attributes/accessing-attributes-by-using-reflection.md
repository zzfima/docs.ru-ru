---
title: "Доступ к атрибутам с помощью отражения (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a4397200b5a2aa5f337dd3479b5405c1a9f245a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a>Доступ к атрибутам с помощью отражения (Visual Basic)
Возможность определения настраиваемых атрибутов и их помещения в собственный исходный код не будет настолько значимой без наличия способа извлечения этих сведений и работы с ними. Отражение позволяет извлекать сведения, определенные с настраиваемыми атрибутами. Основным методом выступает `GetCustomAttributes`, который возвращает массив объектов, являющихся эквивалентами времени выполнения атрибутов исходного кода. Для этого метода существует несколько перегруженных версий. Для получения дополнительной информации см. <xref:System.Attribute>.  
  
 Спецификация атрибута, например:  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 концептуально эквивалентна следующему коду:  
  
```vb  
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")  
anonymousAuthorObject.version = 1.1  
```  
  
 Однако код не выполняется до тех пор, пока у `SampleClass` не будут запрошены атрибуты. Вызов `GetCustomAttributes` в `SampleClass` приведет к тому, что объект `Author` будет создан и инициализирован так, как показано выше. Если класс имеет другие атрибуты, другие объекты атрибутов создаются аналогично. `GetCustomAttributes` затем возвращает объект `Author` и все другие объекты атрибутов в массиве. Потом можно пройти по этому массиву, определить в зависимости от типа каждого элемента массива какие атрибуты были применены и извлечь сведения из объектов атрибутов.  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример. Определяется настраиваемый атрибут, который применяется к нескольким сущностям и извлекается через отражение.  
  
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
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)  
 [Извлечение информации, сохраненной в атрибуте](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
 [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) (Отражение (Visual Basic))  
 [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)  
 [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Создание настраиваемых атрибутов (Visual Basic))
