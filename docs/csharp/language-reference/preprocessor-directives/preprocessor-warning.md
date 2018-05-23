---
title: '#warning (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: c56458e0100c23450655e48b2abfb346e18e0bb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="warning-c-reference"></a><span data-ttu-id="16999-102">#warning (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="16999-102">#warning (C# Reference)</span></span>
<span data-ttu-id="16999-103">`#warning` позволяет создать предупреждение первого уровня из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="16999-103">`#warning` lets you generate a level one warning from a specific location in your code.</span></span> <span data-ttu-id="16999-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="16999-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="16999-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="16999-105">Remarks</span></span>  
 <span data-ttu-id="16999-106">Как правило, `#warning` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="16999-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="16999-107">Кроме того, с помощью директивы [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) можно создать определяемую пользователем ошибку.</span><span class="sxs-lookup"><span data-stu-id="16999-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16999-108">Пример</span><span class="sxs-lookup"><span data-stu-id="16999-108">Example</span></span>  
  
```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="16999-109">См. также</span><span class="sxs-lookup"><span data-stu-id="16999-109">See Also</span></span>  
 [<span data-ttu-id="16999-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="16999-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="16999-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="16999-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="16999-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="16999-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
