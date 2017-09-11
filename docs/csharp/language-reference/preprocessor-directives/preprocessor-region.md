---
title: "#<a name=\"region-c-reference\"></a>region (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#region'
dev_langs:
- CSharp
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f7685d23bc1d40a0d0b6c9ac9a644019e1186eb7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="region-c-reference"></a><span data-ttu-id="89fc9-102">#region (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="89fc9-102">#region (C# Reference)</span></span>
<span data-ttu-id="89fc9-103">Директива `#region` позволяет указать блок кода, который можно разворачивать и сворачивать с помощью функции [структурирования](/visualstudio/ide/outlining) в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89fc9-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="89fc9-104">В больших файлах кода удобно сворачивать или скрывать одну или несколько областей, чтобы не отвлекаться от той части файла, над которой в настоящее время идет работа.</span><span class="sxs-lookup"><span data-stu-id="89fc9-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="89fc9-105">В следующем примере показано, как определить область:</span><span class="sxs-lookup"><span data-stu-id="89fc9-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="89fc9-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="89fc9-106">Remarks</span></span>  
 <span data-ttu-id="89fc9-107">В конце блока `#region` должна присутствовать директива [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="89fc9-107">A `#region` block must be terminated with a [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="89fc9-108">Блок `#region` не может накладываться на блок [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="89fc9-108">A `#region` block cannot overlap with a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) block.</span></span> <span data-ttu-id="89fc9-109">Однако блок `#region` можно вложить в блок `#if`, а блок `#if` — в блок `#region`.</span><span class="sxs-lookup"><span data-stu-id="89fc9-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89fc9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="89fc9-110">See Also</span></span>  
 <span data-ttu-id="89fc9-111">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="89fc9-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="89fc9-112">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="89fc9-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="89fc9-113">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="89fc9-113">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

