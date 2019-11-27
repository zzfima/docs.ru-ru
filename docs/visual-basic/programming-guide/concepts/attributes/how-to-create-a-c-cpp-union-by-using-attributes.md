---
title: Инструкции. СозданиеC++ объединения C с помощью атрибутов
ms.date: 07/20/2015
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
ms.openlocfilehash: acb8dc781e2872ae46e5aa058a98b3dd98f3e064
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349501"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="09bed-102">Инструкции. Создание C/C++ Union с помощью атрибутов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09bed-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>

<span data-ttu-id="09bed-103">С помощью атрибутов можно настраивать расположение структур в памяти.</span><span class="sxs-lookup"><span data-stu-id="09bed-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="09bed-104">Например, можно создать так называемое объединение в C/C++ с помощью атрибутов `StructLayout(LayoutKind.Explicit)` и `FieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="09bed-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>

## <a name="example"></a><span data-ttu-id="09bed-105">Пример</span><span class="sxs-lookup"><span data-stu-id="09bed-105">Example</span></span>

<span data-ttu-id="09bed-106">В этом сегменте кода все поля объединения `TestUnion` начинаются с одного адреса в памяти.</span><span class="sxs-lookup"><span data-stu-id="09bed-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>

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

## <a name="example"></a><span data-ttu-id="09bed-107">Пример</span><span class="sxs-lookup"><span data-stu-id="09bed-107">Example</span></span>

<span data-ttu-id="09bed-108">Ниже приведен еще один пример, в котором поля начинаются с разных явно заданных адресов.</span><span class="sxs-lookup"><span data-stu-id="09bed-108">The following is another example where fields start at different explicitly set locations.</span></span>

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

<span data-ttu-id="09bed-109">Два целочисленных поля `i1` и `i2` используют те же адреса памяти, что и `lg`.</span><span class="sxs-lookup"><span data-stu-id="09bed-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="09bed-110">Такое управление расположением структуры полезно при использовании вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="09bed-110">This sort of control over struct layout is useful when using platform invocation.</span></span>

## <a name="see-also"></a><span data-ttu-id="09bed-111">См. также</span><span class="sxs-lookup"><span data-stu-id="09bed-111">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="09bed-112">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09bed-112">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="09bed-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09bed-113">Attributes</span></span>](../../../../standard/attributes/index.md)
- <span data-ttu-id="09bed-114">[Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) (Отражение (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="09bed-114">[Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)</span></span>
- [<span data-ttu-id="09bed-115">Атрибуты (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09bed-115">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)
- <span data-ttu-id="09bed-116">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Создание настраиваемых атрибутов (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="09bed-116">[Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span></span>
- <span data-ttu-id="09bed-117">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Обращение к атрибутам с помощью отражения (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="09bed-117">[Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
