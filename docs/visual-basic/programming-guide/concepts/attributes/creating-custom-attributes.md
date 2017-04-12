---
title: "Создание настраиваемых атрибутов (Visual Basic) | Документы Microsoft"
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
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1aa97a591fdbdfab931a8b5e4f70ec3c00762332
ms.lasthandoff: 03/13/2017

---
# <a name="creating-custom-attributes-visual-basic"></a>Создание настраиваемых атрибутов (Visual Basic)
Можно создать собственные настраиваемые атрибуты, определив класс атрибута, прямо или косвенно наследует класс <xref:System.Attribute>, делает определение определений атрибутов в метаданных и быстро.</xref:System.Attribute> Предположим, что требуется тег типов с именем программиста, который разработал его. Можно определить пользовательский `Author` класса атрибута:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 Имя класса — имя атрибута `Author`. Он является производным от `System.Attribute`, поэтому класс настраиваемых атрибутов. Параметры конструктора являются позиционными параметрами настраиваемого атрибута. В этом примере `name` является позиционным параметром. Все открытые поля чтения и записи или свойства являются именованными параметрами. В этом случае `version` только именем параметра. Обратите внимание на использование `AttributeUsage` атрибута `Author` атрибут допустим только для класса и `Structure` объявления.  
  
 Этот атрибут можно использовать следующим образом:  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 `AttributeUsage`имеет именованный параметр, `AllowMultiple`, с помощью которой можно изменять пользовательский атрибут однократного использования или multiuse. В следующем примере кода создается многократно используемый атрибут.  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 В следующем примере несколько атрибутов одного типа применяются к классу.  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  Если класс атрибута содержит свойство, что свойство должно быть чтения и записи.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection></xref:System.Reflection>   
 [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Написание настраиваемых атрибутов](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc)   
 [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)   
 [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
