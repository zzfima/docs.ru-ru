---
title: '#region. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: ba5b47d77c69761a77b05ac6079e1b003af336b3
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608754"
---
# <a name="region-c-reference"></a><span data-ttu-id="c104a-102">#region (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c104a-102">#region (C# Reference)</span></span>
<span data-ttu-id="c104a-103">Директива `#region` позволяет указать блок кода, который можно разворачивать и сворачивать с помощью функции [структурирования](/visualstudio/ide/outlining) в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c104a-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="c104a-104">В больших файлах кода удобно сворачивать или скрывать одну или несколько областей, чтобы не отвлекаться от той части файла, над которой в настоящее время идет работа.</span><span class="sxs-lookup"><span data-stu-id="c104a-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="c104a-105">В следующем примере показано, как определить область:</span><span class="sxs-lookup"><span data-stu-id="c104a-105">The following example shows how to define a region:</span></span>  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a><span data-ttu-id="c104a-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c104a-106">Remarks</span></span>  
 <span data-ttu-id="c104a-107">В конце блока `#region` должна присутствовать директива [#endregion](./preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="c104a-107">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="c104a-108">Блок `#region` не может накладываться на блок [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="c104a-108">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="c104a-109">Однако блок `#region` можно вложить в блок `#if`, а блок `#if` — в блок `#region`.</span><span class="sxs-lookup"><span data-stu-id="c104a-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c104a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c104a-110">See also</span></span>

- [<span data-ttu-id="c104a-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c104a-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c104a-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c104a-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c104a-113">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="c104a-113">C# Preprocessor Directives</span></span>](./index.md)
