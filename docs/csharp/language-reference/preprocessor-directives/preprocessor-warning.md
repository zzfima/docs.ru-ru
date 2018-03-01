---
title: "#warning (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8145c4a62d5179d6fa46e27186d83fc0108939d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="warning-c-reference"></a><span data-ttu-id="e5dba-102">#warning (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e5dba-102">#warning (C# Reference)</span></span>
<span data-ttu-id="e5dba-103">`#warning` позволяет создать предупреждение первого уровня из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="e5dba-103">`#warning` lets you generate a level one warning from a specific location in your code.</span></span> <span data-ttu-id="e5dba-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="e5dba-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="e5dba-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5dba-105">Remarks</span></span>  
 <span data-ttu-id="e5dba-106">Как правило, `#warning` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="e5dba-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="e5dba-107">Кроме того, с помощью директивы [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) можно создать определяемую пользователем ошибку.</span><span class="sxs-lookup"><span data-stu-id="e5dba-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5dba-108">Пример</span><span class="sxs-lookup"><span data-stu-id="e5dba-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5dba-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e5dba-109">See Also</span></span>  
 [<span data-ttu-id="e5dba-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e5dba-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e5dba-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e5dba-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e5dba-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="e5dba-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
