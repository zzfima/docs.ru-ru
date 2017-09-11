---
title: "#<a name=\"pragma-warning-c-reference\"></a>pragma warning (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma warning'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 75c11acfd096d36c96ceb9e9c5c0d16e47e58fa1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="9ee6a-102">#pragma warning (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9ee6a-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="9ee6a-103">`#pragma warning` может включать или отключать определенные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="9ee6a-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ee6a-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ee6a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ee6a-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="9ee6a-106">Список номеров предупреждений с разделителем-запятой.</span><span class="sxs-lookup"><span data-stu-id="9ee6a-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="9ee6a-107">Префикс CS является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9ee6a-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="9ee6a-108">Если номера предупреждений не указаны, `disable` отключает все предупреждения, а `restore` включает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="9ee6a-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ee6a-109">Чтобы найти номера предупреждений в Visual Studio, выполните сборку проекта, а затем поиск номеров предупреждений в окне **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="9ee6a-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ee6a-110">Пример</span><span class="sxs-lookup"><span data-stu-id="9ee6a-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ee6a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9ee6a-111">See Also</span></span>  
 <span data-ttu-id="9ee6a-112">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9ee6a-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9ee6a-113">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9ee6a-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9ee6a-114">[Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="9ee6a-114">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 [<span data-ttu-id="9ee6a-115">Ошибки компилятора C#</span><span class="sxs-lookup"><span data-stu-id="9ee6a-115">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)

