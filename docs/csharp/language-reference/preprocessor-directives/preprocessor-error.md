---
title: '#error (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: ed43c1f85142ec6c54e44db5e3b0b7de3ef36bb8
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259890"
---
# <a name="error-c-reference"></a><span data-ttu-id="310ef-102">#error (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="310ef-102">#error (C# Reference)</span></span>
<span data-ttu-id="310ef-103">`#error` позволяет создать определяемую пользователем ошибку [CS1029](../compiler-messages/cs1029.md) из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="310ef-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="310ef-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="310ef-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="310ef-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="310ef-105">Remarks</span></span>  
 <span data-ttu-id="310ef-106">Как правило, `#error` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="310ef-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="310ef-107">Кроме того, с помощью директивы [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) можно создать определяемое пользователем предупреждение.</span><span class="sxs-lookup"><span data-stu-id="310ef-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="310ef-108">Пример</span><span class="sxs-lookup"><span data-stu-id="310ef-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="310ef-109">См. также</span><span class="sxs-lookup"><span data-stu-id="310ef-109">See Also</span></span>

- [<span data-ttu-id="310ef-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="310ef-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="310ef-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="310ef-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="310ef-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="310ef-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
