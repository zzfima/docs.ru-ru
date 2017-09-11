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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 195dc0c64cb01e38ede0b7c34c30ca7912aea685
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="ce7f8-102">Практическое руководство: Создание объединения C/C++ с помощью атрибутов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce7f8-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>
<span data-ttu-id="ce7f8-103">С помощью атрибутов можно настраивать расположение структур в памяти.</span><span class="sxs-lookup"><span data-stu-id="ce7f8-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="ce7f8-104">Например, можно создать так называемое объединение в C/C++ с помощью `StructLayout(LayoutKind.Explicit)` и `FieldOffset` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="ce7f8-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce7f8-105">Пример</span><span class="sxs-lookup"><span data-stu-id="ce7f8-105">Example</span></span>  
 <span data-ttu-id="ce7f8-106">В этом сегменте кода все поля `TestUnion` начинаются с одного адреса в памяти.</span><span class="sxs-lookup"><span data-stu-id="ce7f8-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="ce7f8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ce7f8-107">Example</span></span>  
 <span data-ttu-id="ce7f8-108">Ниже приведен еще один пример, где поля начинаются с разных явно заданных адресов.</span><span class="sxs-lookup"><span data-stu-id="ce7f8-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
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
  
 <span data-ttu-id="ce7f8-109">Два целочисленных поля `i1` и `i2`, используют те же адреса памяти как `lg`.</span><span class="sxs-lookup"><span data-stu-id="ce7f8-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="ce7f8-110">Такое управление расположением структуры полезно при использовании вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ce7f8-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7f8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ce7f8-111">See Also</span></span>  
 <span data-ttu-id="ce7f8-112"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="ce7f8-112"><xref:System.Reflection></span></span>   
 <span data-ttu-id="ce7f8-113"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="ce7f8-113"><xref:System.Attribute></span></span>   
<span data-ttu-id="ce7f8-114"> [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ce7f8-114"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="ce7f8-115"> [Атрибуты](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="ce7f8-115"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="ce7f8-116"> [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="ce7f8-116"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="ce7f8-117"> [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="ce7f8-117"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="ce7f8-118"> [Создание настраиваемых атрибутов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="ce7f8-118"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
<span data-ttu-id="ce7f8-119"> [Доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="ce7f8-119"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
