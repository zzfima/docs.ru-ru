---
title: Оператор %= (Справочник по C#)
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: ab3a6a8d5cbfeb4d527ca1f9c233ddfaba3d35ff
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188720"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b0c4e-102">Оператор %= (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b0c4e-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="b0c4e-103">Оператор присваивания остатка.</span><span class="sxs-lookup"><span data-stu-id="b0c4e-103">The remainder assignment operator.</span></span>

<span data-ttu-id="b0c4e-104">Выражение, использующее оператор `%=`, такое как</span><span class="sxs-lookup"><span data-stu-id="b0c4e-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="b0c4e-105">эквивалентно</span><span class="sxs-lookup"><span data-stu-id="b0c4e-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="b0c4e-106">за исключением того, что `x` вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="b0c4e-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="b0c4e-107">[Оператор остатка](remainder-operator.md) `%` вычисляет остаток от деления двух операндов.</span><span class="sxs-lookup"><span data-stu-id="b0c4e-107">The [remainder operator](remainder-operator.md) `%` computes the remainder after division of its operands.</span></span> <span data-ttu-id="b0c4e-108">Он поддерживается всеми числовыми типами данных.</span><span class="sxs-lookup"><span data-stu-id="b0c4e-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="b0c4e-109">Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор остатка](remainder-operator.md) `%`, оператор присваивания остатка `%=` неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="b0c4e-109">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="b0c4e-110">В следующем примере иллюстрируется использование оператора `%=`.</span><span class="sxs-lookup"><span data-stu-id="b0c4e-110">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="b0c4e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b0c4e-111">See also</span></span>

- [<span data-ttu-id="b0c4e-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b0c4e-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b0c4e-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b0c4e-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b0c4e-114">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="b0c4e-114">C# Operators</span></span>](index.md)
