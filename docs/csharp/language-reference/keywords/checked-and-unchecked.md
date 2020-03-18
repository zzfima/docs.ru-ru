---
title: Справочник по C#. Checked и Unchecked
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 8ee4c481a30dce30029fbe8cc26f4798b523a7ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173644"
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="9b8e7-102">Checked и Unchecked (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9b8e7-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="9b8e7-103">Строка кода C# может выполняться как в проверенном, так и в непроверенном контексте.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="9b8e7-104">В проверенном контексте арифметическое переполнение создает исключение.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="9b8e7-105">В непроверяемом контексте арифметическое переполнение игнорируется и результат усекается путем удаления старших разрядов, которые не помещаются в целевой тип данных.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
- <span data-ttu-id="9b8e7-106">[checked](checked.md). Укажите проверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-106">[checked](checked.md) Specify checked context.</span></span>  
  
- <span data-ttu-id="9b8e7-107">[unchecked](unchecked.md). Укажите непроверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-107">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="9b8e7-108">Следующие операции не затрагиваются проверкой переполнения.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-108">The following operations are affected by the overflow checking:</span></span>  
  
- <span data-ttu-id="9b8e7-109">Выражения, использующие следующие предопределенные операторы на целочисленных типах:</span><span class="sxs-lookup"><span data-stu-id="9b8e7-109">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="9b8e7-110">`++`, `--`; унарные `-`, `+`, `-`, `*`, `/`.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-110">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
- <span data-ttu-id="9b8e7-111">Явные числовые преобразования между целочисленными типами либо из `float` или `double` в целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-111">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="9b8e7-112">Если ни `checked`, ни `unchecked` не указаны, контекст по умолчанию для неконстантных выражений (выражения, вычисляемые во время выполнения) определяется по значению параметра компилятора [-checked](../compiler-options/checked-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="9b8e7-112">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="9b8e7-113">По умолчанию значение этого параметра не задано, и арифметические операции выполняются в непроверенном контексте.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-113">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>

 <span data-ttu-id="9b8e7-114">Для константных выражений (выражения, которые можно полностью вычислить во время компиляции) контекстом по умолчанию является проверяемый.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-114">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="9b8e7-115">Если только константное выражение явным образом не размещено в непроверенном контексте, переполнения, возникающие при вычислении выражения во время компиляции, вызывают ошибки времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="9b8e7-115">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b8e7-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9b8e7-116">See also</span></span>

- [<span data-ttu-id="9b8e7-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9b8e7-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9b8e7-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9b8e7-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9b8e7-119">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9b8e7-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9b8e7-120">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="9b8e7-120">Statement Keywords</span></span>](statement-keywords.md)
