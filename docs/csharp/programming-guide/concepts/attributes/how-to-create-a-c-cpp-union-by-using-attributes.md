---
title: "Практическое руководство. Создание объединения C/C++ с помощью атрибутов (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e9274b585c2fecf53b94d94f9bdfdaf4a47f1041
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="ebf58-102">Практическое руководство. Создание объединения C/C++ с помощью атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="ebf58-102">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>
<span data-ttu-id="ebf58-103">С помощью атрибутов можно настраивать расположение структур в памяти.</span><span class="sxs-lookup"><span data-stu-id="ebf58-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="ebf58-104">Например, можно создать так называемое объединение в C/C++ с помощью атрибутов `StructLayout(LayoutKind.Explicit)` и `FieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="ebf58-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebf58-105">Пример</span><span class="sxs-lookup"><span data-stu-id="ebf58-105">Example</span></span>  
 <span data-ttu-id="ebf58-106">В этом сегменте кода все поля объединения `TestUnion` начинаются с одного адреса в памяти.</span><span class="sxs-lookup"><span data-stu-id="ebf58-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestUnion  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public byte b;  
       }  
```  
  
## <a name="example"></a><span data-ttu-id="ebf58-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ebf58-107">Example</span></span>  
 <span data-ttu-id="ebf58-108">Ниже приведен еще один пример, в котором поля начинаются с разных явно заданных адресов.</span><span class="sxs-lookup"><span data-stu-id="ebf58-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestExplicit  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public long lg;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i1;  
  
           [System.Runtime.InteropServices.FieldOffset(4)]  
           public int i2;  
  
           [System.Runtime.InteropServices.FieldOffset(8)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(12)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(14)]  
           public byte b;  
       }  
```  
  
 <span data-ttu-id="ebf58-109">Два целочисленных поля `i1` и `i2` используют те же адреса памяти, что и `lg`.</span><span class="sxs-lookup"><span data-stu-id="ebf58-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="ebf58-110">Такое управление расположением структуры полезно при использовании вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ebf58-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf58-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ebf58-111">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="ebf58-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ebf58-112">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ebf58-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ebf58-113">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)  
 <span data-ttu-id="ebf58-114">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) (Отражение (C#))</span><span class="sxs-lookup"><span data-stu-id="ebf58-114">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md)</span></span>  
 [<span data-ttu-id="ebf58-115">Атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="ebf58-115">Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="ebf58-116">Создание настраиваемых атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="ebf58-116">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="ebf58-117">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="ebf58-117">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
