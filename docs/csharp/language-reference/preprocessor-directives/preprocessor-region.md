---
title: '#region. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: adaa58fc47da557a31270e99ff8a1dae3d0731bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724035"
---
# <a name="region-c-reference"></a><span data-ttu-id="d98a4-102">#region (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d98a4-102">#region (C# Reference)</span></span>
<span data-ttu-id="d98a4-103">Директива `#region` позволяет указать блок кода, который можно разворачивать и сворачивать с помощью функции [структурирования](/visualstudio/ide/outlining) в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d98a4-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="d98a4-104">В больших файлах кода удобно сворачивать или скрывать одну или несколько областей, чтобы не отвлекаться от той части файла, над которой в настоящее время идет работа.</span><span class="sxs-lookup"><span data-stu-id="d98a4-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="d98a4-105">В следующем примере показано, как определить область:</span><span class="sxs-lookup"><span data-stu-id="d98a4-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="d98a4-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="d98a4-106">Remarks</span></span>  
 <span data-ttu-id="d98a4-107">В конце блока `#region` должна присутствовать директива [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="d98a4-107">A `#region` block must be terminated with a [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="d98a4-108">Блок `#region` не может накладываться на блок [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="d98a4-108">A `#region` block cannot overlap with a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) block.</span></span> <span data-ttu-id="d98a4-109">Однако блок `#region` можно вложить в блок `#if`, а блок `#if` — в блок `#region`.</span><span class="sxs-lookup"><span data-stu-id="d98a4-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d98a4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d98a4-110">See also</span></span>

- [<span data-ttu-id="d98a4-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d98a4-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d98a4-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d98a4-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d98a4-113">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="d98a4-113">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
