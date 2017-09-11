---
title: "#<a name=\"warning-c-reference\"></a>warning (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#warning'
dev_langs:
- CSharp
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
caps.latest.revision: 9
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
ms.openlocfilehash: 8630101a90bd6d4ed2036b495b254c9475531dc0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="warning-c-reference"></a><span data-ttu-id="1b276-102">#warning (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1b276-102">#warning (C# Reference)</span></span>
<span data-ttu-id="1b276-103">`#warning` позволяет создать предупреждение первого уровня из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="1b276-103">`#warning` lets you generate a level one warning from a specific location in your code.</span></span> <span data-ttu-id="1b276-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="1b276-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="1b276-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b276-105">Remarks</span></span>  
 <span data-ttu-id="1b276-106">Как правило, `#warning` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="1b276-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="1b276-107">Кроме того, с помощью директивы [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) можно создать определяемую пользователем ошибку.</span><span class="sxs-lookup"><span data-stu-id="1b276-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b276-108">Пример</span><span class="sxs-lookup"><span data-stu-id="1b276-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b276-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1b276-109">See Also</span></span>  
 <span data-ttu-id="1b276-110">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1b276-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1b276-111">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1b276-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="1b276-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="1b276-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

