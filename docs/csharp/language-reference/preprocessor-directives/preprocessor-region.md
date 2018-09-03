---
title: '#region (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: 3edc4fe757ab1f5cbf42e67ab74cd8032a82d853
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463277"
---
# <a name="region-c-reference"></a><span data-ttu-id="1d21f-102">#region (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1d21f-102">#region (C# Reference)</span></span>
<span data-ttu-id="1d21f-103">Директива `#region` позволяет указать блок кода, который можно разворачивать и сворачивать с помощью функции [структурирования](/visualstudio/ide/outlining) в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1d21f-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="1d21f-104">В больших файлах кода удобно сворачивать или скрывать одну или несколько областей, чтобы не отвлекаться от той части файла, над которой в настоящее время идет работа.</span><span class="sxs-lookup"><span data-stu-id="1d21f-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="1d21f-105">В следующем примере показано, как определить область:</span><span class="sxs-lookup"><span data-stu-id="1d21f-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="1d21f-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d21f-106">Remarks</span></span>  
 <span data-ttu-id="1d21f-107">В конце блока `#region` должна присутствовать директива [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="1d21f-107">A `#region` block must be terminated with a [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="1d21f-108">Блок `#region` не может накладываться на блок [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="1d21f-108">A `#region` block cannot overlap with a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) block.</span></span> <span data-ttu-id="1d21f-109">Однако блок `#region` можно вложить в блок `#if`, а блок `#if` — в блок `#region`.</span><span class="sxs-lookup"><span data-stu-id="1d21f-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d21f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1d21f-110">See Also</span></span>

- [<span data-ttu-id="1d21f-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1d21f-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="1d21f-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1d21f-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1d21f-113">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="1d21f-113">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
