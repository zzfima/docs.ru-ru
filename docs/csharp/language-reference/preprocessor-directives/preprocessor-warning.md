---
title: '#warning (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 59ca63d5089e377627a9116f24f9a0a1681bb4b2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43461687"
---
# <a name="warning-c-reference"></a><span data-ttu-id="577cc-102">#warning (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="577cc-102">#warning (C# Reference)</span></span>
<span data-ttu-id="577cc-103">`#warning` позволяет создать предупреждение компилятора [CS1030](../../misc/cs1030.md) первого уровня из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="577cc-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="577cc-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="577cc-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="577cc-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="577cc-105">Remarks</span></span>
 <span data-ttu-id="577cc-106">Как правило, `#warning` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="577cc-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="577cc-107">Кроме того, с помощью директивы [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) можно создать определяемую пользователем ошибку.</span><span class="sxs-lookup"><span data-stu-id="577cc-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="577cc-108">Пример</span><span class="sxs-lookup"><span data-stu-id="577cc-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="577cc-109">См. также</span><span class="sxs-lookup"><span data-stu-id="577cc-109">See Also</span></span>

- [<span data-ttu-id="577cc-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="577cc-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="577cc-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="577cc-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="577cc-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="577cc-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
