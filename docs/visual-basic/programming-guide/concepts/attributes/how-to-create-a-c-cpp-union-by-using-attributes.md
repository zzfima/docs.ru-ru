---
title: "Практическое руководство: Создание объединения C C++ с помощью атрибутов (Visual Basic) | Документы Microsoft"
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
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ff1686328630b233b25839c79d0009d48aab5ab
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a>Практическое руководство: Создание объединения C/C++ с помощью атрибутов (Visual Basic)
С помощью атрибутов можно настраивать расположение структур в памяти. Например, можно создать так называемое объединение в C/C++ с помощью `StructLayout(LayoutKind.Explicit)` и `FieldOffset` атрибуты.  
  
## <a name="example"></a>Пример  
 В этом сегменте кода все поля `TestUnion` начинаются с одного адреса в памяти.  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
<System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestUnion  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public i As Integer  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public d As Double  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public c As Char  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public b As Byte  
End Structure  
```  
  
## <a name="example"></a>Пример  
 Ниже приведен еще один пример, где поля начинаются с разных явно заданных адресов.  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
 <System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestExplicit  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public lg As Long  
  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public i1 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(4)>   
     Public i2 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(8)>   
     Public d As Double  
  
     <System.Runtime.InteropServices.FieldOffset(12)>   
     Public c As Char  
  
     <System.Runtime.InteropServices.FieldOffset(14)>   
     Public b As Byte  
 End Structure  
```  
  
 Два целочисленных поля `i1` и `i2`, используют те же адреса памяти как `lg`. Такое управление расположением структуры полезно при использовании вызова неуправляемого кода.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Атрибуты](https://msdn.microsoft.com/library/5x6cd29c)   
 [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Создание настраиваемых атрибутов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)   
 [Доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
