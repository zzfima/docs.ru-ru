---
title: '#Справочник по C#. #pragma warning'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 3b50585e0ae0964cf19379573bd85923daa552f4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242741"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="5c5cd-102">#pragma warning (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5c5cd-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="5c5cd-103">`#pragma warning` может включать или отключать определенные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="5c5cd-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c5cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c5cd-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c5cd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c5cd-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="5c5cd-106">Список номеров предупреждений с разделителем-запятой.</span><span class="sxs-lookup"><span data-stu-id="5c5cd-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="5c5cd-107">Префикс CS является необязательным.</span><span class="sxs-lookup"><span data-stu-id="5c5cd-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="5c5cd-108">Если номера предупреждений не указаны, `disable` отключает все предупреждения, а `restore` включает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="5c5cd-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c5cd-109">Чтобы найти номера предупреждений в Visual Studio, выполните сборку проекта, а затем поиск номеров предупреждений в окне **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="5c5cd-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c5cd-110">Пример</span><span class="sxs-lookup"><span data-stu-id="5c5cd-110">Example</span></span>  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c5cd-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5c5cd-111">See Also</span></span>

- [<span data-ttu-id="5c5cd-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5c5cd-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="5c5cd-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5c5cd-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5c5cd-114">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="5c5cd-114">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [<span data-ttu-id="5c5cd-115">Ошибки компилятора C#</span><span class="sxs-lookup"><span data-stu-id="5c5cd-115">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
