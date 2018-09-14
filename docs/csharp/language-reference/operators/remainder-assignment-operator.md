---
title: Оператор %= (Справочник по C#)
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: c475517666bdadaa457dbb4188808b3a96fcdf0e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085651"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f1ee4-102">Оператор %= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f1ee4-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="f1ee4-103">Оператор присваивания остатка.</span><span class="sxs-lookup"><span data-stu-id="f1ee4-103">The remainder assignment operator.</span></span>

<span data-ttu-id="f1ee4-104">Выражение, использующее оператор `%=`, такое как</span><span class="sxs-lookup"><span data-stu-id="f1ee4-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="f1ee4-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="f1ee4-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="f1ee4-106">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="f1ee4-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="f1ee4-107">[Оператор остатка](remainder-operator.md) `%` поддерживается всеми числовыми типами и вычисляет остаток от деления своих операндов.</span><span class="sxs-lookup"><span data-stu-id="f1ee4-107">The [remainder operator](remainder-operator.md) `%` is supported by all numeric types and computes the remainder after division of its operands.</span></span>

<span data-ttu-id="f1ee4-108">Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор остатка](remainder-operator.md) `%`, оператор присваивания остатка `%=` неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="f1ee4-108">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="f1ee4-109">В следующем примере иллюстрируется использование оператора `%=`.</span><span class="sxs-lookup"><span data-stu-id="f1ee4-109">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="f1ee4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f1ee4-110">See also</span></span>

- [<span data-ttu-id="f1ee4-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f1ee4-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f1ee4-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f1ee4-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f1ee4-113">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="f1ee4-113">C# Operators</span></span>](index.md)
