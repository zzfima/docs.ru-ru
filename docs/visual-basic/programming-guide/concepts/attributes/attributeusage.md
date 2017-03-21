---
title: "AttributeUsage (Visual Basic) | Документы Microsoft"
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
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
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
ms.openlocfilehash: bf56f40033f9d1547d63fccd25e3c0561bb62cb1
ms.lasthandoff: 03/13/2017

---
# <a name="attributeusage-visual-basic"></a>AttributeUsage (Visual Basic)
Определяет, как можно использовать класс настраиваемых атрибутов. `AttributeUsage`— Это атрибут, который может применяться к определениям настраиваемого атрибута для управления применения нового атрибута. При применении явно, по умолчанию выглядеть следующим образом:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 В этом примере `NewAttribute` класс может быть применен к любой сущности кода, но может применяться только один раз для каждой сущности. Он наследуется производными классами при применении к базовому классу.  
  
 `AllowMultiple` И `Inherited` аргументы являются необязательными, поэтому этот код имеет тот же эффект:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 Первый `AttributeUsage` аргумент должен быть один или несколько элементов <xref:System.AttributeTargets>перечисления.</xref:System.AttributeTargets> Несколько целевых типов можно связать вместе с оператором OR следующим образом:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 Если `AllowMultiple` аргумент имеет значение `true`, а затем полученный атрибут может применяться несколько раз к одной сущности следующим образом:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>   
Class MultiUseAttr  
    Inherits Attribute  
End Class  
  
<MultiUseAttr(), MultiUseAttr()>   
Class Class1  
End Class  
```  
  
 В этом случае `MultiUseAttr` может применяться несколько раз, так как `AllowMultiple` равен `true`. Оба формата для применения нескольких атрибутов являются допустимыми.  
  
 Если `Inherited` равен `false`, то атрибут не наследуется классами, производными от класса, который имеет атрибуты. Пример:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>   
Class Attr1  
    Inherits Attribute  
End Class  
  
<Attr1()>   
Class BClass  
  
End Class    
  
Class DClass  
    Inherits BClass  
End Class  
```  
  
 В этом случае `Attr1` не применяется к `DClass` через наследование.  
  
## <a name="remarks"></a>Примечания  
 `AttributeUsage` Является атрибутом однократного использования — он не может применяться несколько раз в тот же класс. `AttributeUsage`является псевдонимом для <xref:System.AttributeUsageAttribute>.</xref:System.AttributeUsageAttribute>  
  
 Дополнительные сведения см. в разделе [доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется влияние `Inherited` и `AllowMultiple` аргументы `AttributeUsage` атрибут и как можно перечислить настраиваемых атрибутов, примененных к классу.  
  
```vb  
Imports System  
```  
  
```vb  
' Create some custom attributes:  
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>   
Class A1  
    Inherits System.Attribute  
End Class  
  
<AttributeUsage(System.AttributeTargets.Class)>   
Class A2  
    Inherits System.Attribute  
End Class      
  
<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>   
Class A3  
    Inherits System.Attribute  
End Class  
  
' Apply custom attributes to classes:  
<A1(), A2()>   
Class BaseClass  
  
End Class  
  
<A3(), A3()>   
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
Public Class TestAttributeUsage  
    Sub Main()  
        Dim b As New BaseClass  
        Dim d As New DerivedClass  
        ' Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:")  
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)  
  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next  
  
        Console.WriteLine("Attributes on Derived Class:")  
        attrs = d.GetType().GetCustomAttributes(True)  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next              
    End Sub  
End Class  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Attribute></xref:System.Attribute>   
 <xref:System.Reflection></xref:System.Reflection>   
 [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Атрибуты](https://msdn.microsoft.com/library/5x6cd29c)   
 [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Создание настраиваемых атрибутов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)   
 [Доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
