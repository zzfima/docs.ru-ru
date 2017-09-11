---
title: "Checked и Unchecked (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
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
ms.openlocfilehash: 744f59dbf7ee8370010ff76d4e9dde20490de403
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="a34a3-102">Checked и Unchecked (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a34a3-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="a34a3-103">Строка кода C# может выполняться как в проверенном, так и в непроверенном контексте.</span><span class="sxs-lookup"><span data-stu-id="a34a3-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="a34a3-104">В проверенном контексте арифметическое переполнение создает исключение.</span><span class="sxs-lookup"><span data-stu-id="a34a3-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="a34a3-105">В непроверенном контексте арифметическое переполнение игнорируется, а результат усекается.</span><span class="sxs-lookup"><span data-stu-id="a34a3-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="a34a3-106">[checked](../../../csharp/language-reference/keywords/checked.md). Укажите проверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="a34a3-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="a34a3-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md). Укажите непроверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="a34a3-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="a34a3-108">Если не выбран ни `checked`, ни `unchecked` контекст, используется контекст по умолчанию, который зависит от таких внешних факторов, как параметры компилятора.</span><span class="sxs-lookup"><span data-stu-id="a34a3-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="a34a3-109">Следующие операции не затрагиваются проверкой переполнения.</span><span class="sxs-lookup"><span data-stu-id="a34a3-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="a34a3-110">Выражения, использующие следующие предопределенные операторы на целочисленных типах:</span><span class="sxs-lookup"><span data-stu-id="a34a3-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="a34a3-111">`++` `--` - (унарный)   `+` -   `*` `/`</span><span class="sxs-lookup"><span data-stu-id="a34a3-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="a34a3-112">Явные числовые преобразования между целочисленными типами.</span><span class="sxs-lookup"><span data-stu-id="a34a3-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="a34a3-113">Параметр компилятора [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) позволяет указать проверенный или непроверенный контекст для всех целочисленных арифметических выражений, которые явно попадают в область действия ключевого слова `checked` или `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="a34a3-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a34a3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a34a3-114">See Also</span></span>  
 <span data-ttu-id="a34a3-115">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a34a3-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a34a3-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a34a3-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a34a3-117">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a34a3-117">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="a34a3-118">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="a34a3-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)

