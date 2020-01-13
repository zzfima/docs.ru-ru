---
title: '#error. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 7203e1271da66e78bfbd70717b0f5e536a7ebd86
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712524"
---
# <a name="error-c-reference"></a><span data-ttu-id="2733d-102">#error (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2733d-102">#error (C# Reference)</span></span>
<span data-ttu-id="2733d-103">`#error` позволяет создать определяемую пользователем ошибку [CS1029](../compiler-messages/cs1029.md) из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="2733d-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="2733d-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="2733d-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="2733d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="2733d-105">Remarks</span></span>  
 <span data-ttu-id="2733d-106">Как правило, `#error` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="2733d-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="2733d-107">Кроме того, с помощью директивы [#warning](./preprocessor-warning.md) можно создать определяемое пользователем предупреждение.</span><span class="sxs-lookup"><span data-stu-id="2733d-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2733d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="2733d-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2733d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2733d-109">See also</span></span>

- [<span data-ttu-id="2733d-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2733d-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2733d-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2733d-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2733d-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="2733d-112">C# Preprocessor Directives</span></span>](./index.md)
