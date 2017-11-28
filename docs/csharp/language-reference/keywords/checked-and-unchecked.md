---
title: "Checked и Unchecked (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b7b18b39dbfa7ed0818d9ea6e9e62ef79a9f5b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="694af-102">Checked и Unchecked (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="694af-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="694af-103">Строка кода C# может выполняться как в проверенном, так и в непроверенном контексте.</span><span class="sxs-lookup"><span data-stu-id="694af-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="694af-104">В проверенном контексте арифметическое переполнение создает исключение.</span><span class="sxs-lookup"><span data-stu-id="694af-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="694af-105">В непроверенном контексте арифметическое переполнение игнорируется, а результат усекается.</span><span class="sxs-lookup"><span data-stu-id="694af-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="694af-106">[checked](../../../csharp/language-reference/keywords/checked.md). Укажите проверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="694af-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="694af-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md). Укажите непроверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="694af-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="694af-108">Если не выбран ни `checked`, ни `unchecked` контекст, используется контекст по умолчанию, который зависит от таких внешних факторов, как параметры компилятора.</span><span class="sxs-lookup"><span data-stu-id="694af-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="694af-109">Следующие операции не затрагиваются проверкой переполнения.</span><span class="sxs-lookup"><span data-stu-id="694af-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="694af-110">Выражения, использующие следующие предопределенные операторы на целочисленных типах:</span><span class="sxs-lookup"><span data-stu-id="694af-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="694af-111">`++` `--` - (унарный)   `+` -   `*` `/`</span><span class="sxs-lookup"><span data-stu-id="694af-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="694af-112">Явные числовые преобразования между целочисленными типами.</span><span class="sxs-lookup"><span data-stu-id="694af-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="694af-113">Параметр компилятора [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) позволяет указать проверенный или непроверенный контекст для всех целочисленных арифметических выражений, которые явно попадают в область действия ключевого слова `checked` или `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="694af-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="694af-114">См. также</span><span class="sxs-lookup"><span data-stu-id="694af-114">See Also</span></span>  
 [<span data-ttu-id="694af-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="694af-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="694af-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="694af-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="694af-117">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="694af-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="694af-118">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="694af-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)
