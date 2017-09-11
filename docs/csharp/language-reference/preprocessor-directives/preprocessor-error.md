---
title: "#<a name=\"error-c-reference\"></a>error (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#error'
dev_langs:
- CSharp
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
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
ms.openlocfilehash: d2d497d7b8345b94dfc77176bf2b0ca79674e9be
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="error-c-reference"></a><span data-ttu-id="769b3-102">#error (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="769b3-102">#error (C# Reference)</span></span>
<span data-ttu-id="769b3-103">`#error` позволяет создать ошибку из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="769b3-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="769b3-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="769b3-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="769b3-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="769b3-105">Remarks</span></span>  
 <span data-ttu-id="769b3-106">Как правило, `#error` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="769b3-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="769b3-107">Кроме того, с помощью директивы [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) можно создать определяемое пользователем предупреждение.</span><span class="sxs-lookup"><span data-stu-id="769b3-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="769b3-108">Пример</span><span class="sxs-lookup"><span data-stu-id="769b3-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="769b3-109">См. также</span><span class="sxs-lookup"><span data-stu-id="769b3-109">See Also</span></span>  
 <span data-ttu-id="769b3-110">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="769b3-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="769b3-111">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="769b3-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="769b3-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="769b3-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

