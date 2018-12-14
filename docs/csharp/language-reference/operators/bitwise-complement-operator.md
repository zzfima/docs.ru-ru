---
title: Оператор ~ (справочник по C#)
ms.date: 11/05/2018
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 1bcb07c5639a098e3a8c566e92083ca0d48efb81
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153219"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="56098-102">Оператор ~ (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="56098-102">~ Operator (C# Reference)</span></span>

<span data-ttu-id="56098-103">Оператор битового дополнения `~` — это унарный оператор, который создает битовое дополнение своего операнда с инвертированием каждого бита.</span><span class="sxs-lookup"><span data-stu-id="56098-103">The bitwise complement operator `~` is a unary operator that produces a bitwise complement of its operand by reversing each bit.</span></span> <span data-ttu-id="56098-104">Оператор `~` поддерживает все целочисленные типы.</span><span class="sxs-lookup"><span data-stu-id="56098-104">All integer types support the `~` operator.</span></span>

> [!NOTE]
> <span data-ttu-id="56098-105">Символ `~` также используется для объявления методов завершения.</span><span class="sxs-lookup"><span data-stu-id="56098-105">The `~` symbol is also used to declare finalizers.</span></span> <span data-ttu-id="56098-106">Дополнительные сведения см. в разделе [Методы завершения](../../programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="56098-106">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

<span data-ttu-id="56098-107">В следующем примере иллюстрируется использование оператора `~`.</span><span class="sxs-lookup"><span data-stu-id="56098-107">The following example demonstrates the usage of the `~` operator:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/snippets/csharp/language-reference/operators/BitwiseComplementExamples.cs#Example)]

> [!NOTE]
> <span data-ttu-id="56098-108">В предыдущем примере используются двоичные литералы, [впервые появившиеся в C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) и [улучшенные в C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span><span class="sxs-lookup"><span data-stu-id="56098-108">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced  in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="56098-109">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="56098-109">Operator overloadability</span></span>

<span data-ttu-id="56098-110">Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `~`.</span><span class="sxs-lookup"><span data-stu-id="56098-110">User-defined types can [overload](../keywords/operator.md) the `~` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="56098-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="56098-111">C# language specification</span></span>

<span data-ttu-id="56098-112">Дополнительные сведения см. в разделе об [операторе битового дополнения](~/_csharplang/spec/expressions.md#bitwise-complement-operator) статьи [Предварительная спецификация C# 6.0](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="56098-112">For more information, see the [Bitwise complement operator](~/_csharplang/spec/expressions.md#bitwise-complement-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56098-113">См. также</span><span class="sxs-lookup"><span data-stu-id="56098-113">See also</span></span>

- [<span data-ttu-id="56098-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="56098-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="56098-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="56098-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="56098-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="56098-116">C# Operators</span></span>](index.md)
- [<span data-ttu-id="56098-117">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="56098-117">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)
- [<span data-ttu-id="56098-118">Оператор &</span><span class="sxs-lookup"><span data-stu-id="56098-118">& operator</span></span>](and-operator.md)
- [<span data-ttu-id="56098-119">Оператор |</span><span class="sxs-lookup"><span data-stu-id="56098-119">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="56098-120">Оператор ^</span><span class="sxs-lookup"><span data-stu-id="56098-120">^ operator</span></span>](xor-operator.md)
