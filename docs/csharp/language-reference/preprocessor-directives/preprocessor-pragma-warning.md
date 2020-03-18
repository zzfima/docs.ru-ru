---
title: '#Справочник по C#. #pragma warning'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 5620ea9e5f31c22e26bee95a450335bb179ced25
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712472"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="8ef59-102">#pragma warning (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8ef59-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="8ef59-103">`#pragma warning` может включать или отключать определенные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="8ef59-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef59-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ef59-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ef59-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ef59-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="8ef59-106">Список номеров предупреждений с разделителем-запятой.</span><span class="sxs-lookup"><span data-stu-id="8ef59-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="8ef59-107">Префикс CS является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8ef59-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="8ef59-108">Если номера предупреждений не указаны, `disable` отключает все предупреждения, а `restore` включает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="8ef59-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ef59-109">Чтобы найти номера предупреждений в Visual Studio, выполните сборку проекта, а затем поиск номеров предупреждений в окне **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="8ef59-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ef59-110">Пример</span><span class="sxs-lookup"><span data-stu-id="8ef59-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8ef59-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8ef59-111">See also</span></span>

- [<span data-ttu-id="8ef59-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8ef59-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8ef59-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8ef59-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8ef59-114">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="8ef59-114">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="8ef59-115">Ошибки компилятора C#</span><span class="sxs-lookup"><span data-stu-id="8ef59-115">C# Compiler Errors</span></span>](../compiler-messages/index.md)
