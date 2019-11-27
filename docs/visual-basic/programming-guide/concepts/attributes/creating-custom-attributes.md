---
title: Создание настраиваемых атрибутов
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 773a3e8e974f37a1554892dd3441c115681c5bae
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350149"
---
# <a name="creating-custom-attributes-visual-basic"></a>Создание настраиваемых атрибутов (Visual Basic)

Собственные настраиваемые атрибуты можно создать, определив класс атрибута, то есть класс, прямо или косвенно наследующий от <xref:System.Attribute>, который упрощает задание определений атрибутов в метаданных. Предположим, что требуется пометить тип тегом с именем программиста, который его разработал. Вы можете определить класс настраиваемых атрибутов `Author`:

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

Имя класса — это имя атрибута, `Author`. Он является производным от `System.Attribute`, поэтому это класс настраиваемых атрибутов. Параметры конструктора являются позиционными параметрами настраиваемого атрибута. В этом примере `name` является позиционным параметром. Все открытые поля или свойства, доступные для чтения и записи, являются именованными параметрами. В этом случае `version` — единственный именованный параметр. Обратите внимание на использование атрибута `AttributeUsage`, делающего атрибут `Author` допустимым только для класса и объявлений `Structure`.

Этот атрибут можно использовать следующим образом:

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

`AttributeUsage` имеет именованный параметр, `AllowMultiple`, с помощью которого можно задавать для настраиваемого атрибута однократное или многократное использование. В следующем примере кода создается многократно используемый атрибут.

```vb
' multiuse attribute
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct,
                       AllowMultiple:=True)>
Public Class Author
    Inherits System.Attribute
```

В следующем примере кода несколько атрибутов одного типа применяются к классу.

```vb
<Author("P. Ackerman", Version:=1.1),
Author("R. Koch", Version:=1.2)>
Class SampleClass
    ' P. Ackerman's code goes here...
    ' R. Koch's code goes here...
End Class
```

> [!NOTE]
> Если класс атрибутов содержит свойство, это свойство должно быть доступно для чтения и записи.

## <a name="see-also"></a>См. также

- <xref:System.Reflection>
- [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)
- [Написание настраиваемых атрибутов](../../../../standard/attributes/writing-custom-attributes.md)
- [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) (Отражение (Visual Basic))
- [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)
- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic))
- [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
