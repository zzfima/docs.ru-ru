---
title: "#error (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23528ae81e4ddca23c67c937ca2588ab4c982e98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="error-c-reference"></a><span data-ttu-id="0ad6c-102">#error (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0ad6c-102">#error (C# Reference)</span></span>
<span data-ttu-id="0ad6c-103">`#error` позволяет создать ошибку из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="0ad6c-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="0ad6c-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="0ad6c-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="0ad6c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ad6c-105">Remarks</span></span>  
 <span data-ttu-id="0ad6c-106">Как правило, `#error` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="0ad6c-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="0ad6c-107">Кроме того, с помощью директивы [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) можно создать определяемое пользователем предупреждение.</span><span class="sxs-lookup"><span data-stu-id="0ad6c-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ad6c-108">Пример</span><span class="sxs-lookup"><span data-stu-id="0ad6c-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ad6c-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0ad6c-109">See Also</span></span>  
 [<span data-ttu-id="0ad6c-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0ad6c-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0ad6c-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0ad6c-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0ad6c-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="0ad6c-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
