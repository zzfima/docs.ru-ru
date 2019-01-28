---
title: '#warning. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 55768a354b2841021607ed40b4ef87b9767edcad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620322"
---
# <a name="warning-c-reference"></a><span data-ttu-id="5736f-102">#warning (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5736f-102">#warning (C# Reference)</span></span>
<span data-ttu-id="5736f-103">`#warning` позволяет создать предупреждение компилятора [CS1030](../../misc/cs1030.md) первого уровня из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="5736f-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="5736f-104">Например:</span><span class="sxs-lookup"><span data-stu-id="5736f-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="5736f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="5736f-105">Remarks</span></span>
 <span data-ttu-id="5736f-106">Как правило, `#warning` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="5736f-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="5736f-107">Кроме того, с помощью директивы [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) можно создать определяемую пользователем ошибку.</span><span class="sxs-lookup"><span data-stu-id="5736f-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5736f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="5736f-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="5736f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5736f-109">See also</span></span>

- [<span data-ttu-id="5736f-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5736f-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="5736f-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5736f-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5736f-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="5736f-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
