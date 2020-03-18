---
title: '#error. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 28e77304edee617adc1422e6a52d0a617cd9b3bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173410"
---
# <a name="error-c-reference"></a><span data-ttu-id="1366b-102">#error (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1366b-102">#error (C# Reference)</span></span>
<span data-ttu-id="1366b-103">`#error` позволяет создать определяемую пользователем ошибку [CS1029](../compiler-messages/cs1029.md) из определенного места в коде.</span><span class="sxs-lookup"><span data-stu-id="1366b-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="1366b-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="1366b-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="1366b-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="1366b-105">Remarks</span></span>  
 <span data-ttu-id="1366b-106">Как правило, `#error` применяется в условной директиве.</span><span class="sxs-lookup"><span data-stu-id="1366b-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="1366b-107">Кроме того, с помощью директивы [#warning](./preprocessor-warning.md) можно создать определяемое пользователем предупреждение.</span><span class="sxs-lookup"><span data-stu-id="1366b-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1366b-108">Пример</span><span class="sxs-lookup"><span data-stu-id="1366b-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1366b-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1366b-109">See also</span></span>

- [<span data-ttu-id="1366b-110">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1366b-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1366b-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1366b-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1366b-112">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="1366b-112">C# Preprocessor Directives</span></span>](./index.md)
