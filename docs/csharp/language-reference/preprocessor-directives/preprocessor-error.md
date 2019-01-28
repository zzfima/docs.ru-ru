---
title: '#error. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 3aa31ce7e189684bd60c238905df3bcbd1818ed6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559347"
---
# <a name="error-c-reference"></a><span data-ttu-id="e0800-102">#error (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e0800-102">#error (C# Reference)</span></span>
<span data-ttu-id="e0800-103">`#error` позволяет создать определяемую пользователем ошибку [CS1029](../compiler-messages/cs1029.md) из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="e0800-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="e0800-104">Например:</span><span class="sxs-lookup"><span data-stu-id="e0800-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="e0800-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0800-105">Remarks</span></span>  
 <span data-ttu-id="e0800-106">Как правило, `#error` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="e0800-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="e0800-107">Кроме того, с помощью директивы [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) можно создать определяемое пользователем предупреждение.</span><span class="sxs-lookup"><span data-stu-id="e0800-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0800-108">Пример</span><span class="sxs-lookup"><span data-stu-id="e0800-108">Example</span></span>  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0800-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e0800-109">See also</span></span>

- [<span data-ttu-id="e0800-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e0800-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="e0800-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e0800-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e0800-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="e0800-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
