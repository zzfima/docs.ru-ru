---
title: Справочник по C#. Checked и Unchecked
ms.custom: seodec18
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 3378cffc1dcee7bb12705704e66b7fdd287105fb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592986"
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="f9c17-102">Checked и Unchecked (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f9c17-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="f9c17-103">Строка кода C# может выполняться как в проверенном, так и в непроверенном контексте.</span><span class="sxs-lookup"><span data-stu-id="f9c17-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="f9c17-104">В проверенном контексте арифметическое переполнение создает исключение.</span><span class="sxs-lookup"><span data-stu-id="f9c17-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="f9c17-105">В непроверяемом контексте арифметическое переполнение игнорируется и результат усекается путем удаления старших разрядов, которые не помещаются в целевой тип данных.</span><span class="sxs-lookup"><span data-stu-id="f9c17-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
- <span data-ttu-id="f9c17-106">[checked](checked.md). Укажите проверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="f9c17-106">[checked](checked.md) Specify checked context.</span></span>  
  
- <span data-ttu-id="f9c17-107">[unchecked](unchecked.md). Укажите непроверенный контекст.</span><span class="sxs-lookup"><span data-stu-id="f9c17-107">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="f9c17-108">Следующие операции не затрагиваются проверкой переполнения.</span><span class="sxs-lookup"><span data-stu-id="f9c17-108">The following operations are affected by the overflow checking:</span></span>  
  
- <span data-ttu-id="f9c17-109">Выражения, использующие следующие предопределенные операторы на целочисленных типах:</span><span class="sxs-lookup"><span data-stu-id="f9c17-109">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="f9c17-110">`++`, `--`; унарные `-`, `+`, `-`, `*`, `/`.</span><span class="sxs-lookup"><span data-stu-id="f9c17-110">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
- <span data-ttu-id="f9c17-111">Явные числовые преобразования между целочисленными типами либо из `float` или `double` в целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="f9c17-111">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="f9c17-112">Если ни `checked`, ни `unchecked` не указаны, контекст по умолчанию для неконстантных выражений (выражения, вычисляемые во время выполнения) определяется по значению параметра компилятора [-checked](../compiler-options/checked-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f9c17-112">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="f9c17-113">По умолчанию значение этого параметра не задано, и арифметические операции выполняются в непроверенном контексте.</span><span class="sxs-lookup"><span data-stu-id="f9c17-113">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>
 
 <span data-ttu-id="f9c17-114">Для константных выражений (выражения, которые можно полностью вычислить во время компиляции) контекстом по умолчанию является проверяемый.</span><span class="sxs-lookup"><span data-stu-id="f9c17-114">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="f9c17-115">Если только константное выражение явным образом не размещено в непроверенном контексте, переполнения, возникающие при вычислении выражения во время компиляции, вызывают ошибки времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="f9c17-115">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f9c17-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f9c17-116">See also</span></span>

- [<span data-ttu-id="f9c17-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f9c17-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f9c17-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f9c17-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f9c17-119">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f9c17-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f9c17-120">Ключевые слова инструкций</span><span class="sxs-lookup"><span data-stu-id="f9c17-120">Statement Keywords</span></span>](statement-keywords.md)
