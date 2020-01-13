---
title: '#Справочник по C#. #pragma warning'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 5620ea9e5f31c22e26bee95a450335bb179ced25
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712472"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="a654c-102">#pragma warning (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a654c-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="a654c-103">`#pragma warning` может включать или отключать определенные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="a654c-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a654c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a654c-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="a654c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a654c-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="a654c-106">Список номеров предупреждений с разделителем-запятой.</span><span class="sxs-lookup"><span data-stu-id="a654c-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="a654c-107">Префикс CS является необязательным.</span><span class="sxs-lookup"><span data-stu-id="a654c-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="a654c-108">Если номера предупреждений не указаны, `disable` отключает все предупреждения, а `restore` включает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="a654c-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a654c-109">Чтобы найти номера предупреждений в Visual Studio, выполните сборку проекта, а затем поиск номеров предупреждений в окне **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="a654c-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a654c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a654c-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a654c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a654c-111">See also</span></span>

- [<span data-ttu-id="a654c-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a654c-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a654c-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a654c-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a654c-114">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="a654c-114">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="a654c-115">Ошибки компилятора C#</span><span class="sxs-lookup"><span data-stu-id="a654c-115">C# Compiler Errors</span></span>](../compiler-messages/index.md)
