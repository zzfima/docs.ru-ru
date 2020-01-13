---
title: '#warning. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 38c3807a696599390667060d3bf374c68845fed0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715072"
---
# <a name="warning-c-reference"></a><span data-ttu-id="bab68-102">#warning (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bab68-102">#warning (C# Reference)</span></span>
<span data-ttu-id="bab68-103">`#warning` позволяет создать предупреждение компилятора [CS1030](../../misc/cs1030.md) первого уровня из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="bab68-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="bab68-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="bab68-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="bab68-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="bab68-105">Remarks</span></span>
 <span data-ttu-id="bab68-106">Как правило, `#warning` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="bab68-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="bab68-107">Кроме того, с помощью директивы [#error](./preprocessor-error.md) можно создать определяемую пользователем ошибку.</span><span class="sxs-lookup"><span data-stu-id="bab68-107">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bab68-108">Пример</span><span class="sxs-lookup"><span data-stu-id="bab68-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="bab68-109">См. также</span><span class="sxs-lookup"><span data-stu-id="bab68-109">See also</span></span>

- [<span data-ttu-id="bab68-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bab68-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bab68-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bab68-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bab68-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="bab68-112">C# Preprocessor Directives</span></span>](./index.md)
