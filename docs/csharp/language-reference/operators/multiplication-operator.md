---
title: '* Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977348"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="09020-102">Справочник по C#. Оператор \*</span><span class="sxs-lookup"><span data-stu-id="09020-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="09020-103">Оператор `*` поддерживается в двух формах: унарный оператор косвенного обращения к указателю или бинарный оператор умножения.</span><span class="sxs-lookup"><span data-stu-id="09020-103">The `*` operator is supported in two forms: a unary pointer indirection operator or a binary multiplication operator.</span></span>

## <a name="pointer-indirection-operator"></a><span data-ttu-id="09020-104">Оператор косвенного обращения к указателю</span><span class="sxs-lookup"><span data-stu-id="09020-104">Pointer indirection operator</span></span>

<span data-ttu-id="09020-105">Используйте унарный оператор `*` для получения переменной, на который указывает операнд типа указателя.</span><span class="sxs-lookup"><span data-stu-id="09020-105">Use the unary `*` operator to obtain the variable to which an operand of a pointer type points.</span></span> <span data-ttu-id="09020-106">Дополнительные сведения см. в [практическом руководстве по получению значения переменной указателя](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span><span class="sxs-lookup"><span data-stu-id="09020-106">For more information, see [How to: obtain the value of a pointer variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span></span>

<span data-ttu-id="09020-107">Для оператора косвенного обращения к указателю `*` требуется контекст [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="09020-107">The pointer indirection operator `*` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="multiplication-operator"></a><span data-ttu-id="09020-108">Оператор умножения</span><span class="sxs-lookup"><span data-stu-id="09020-108">Multiplication operator</span></span>

<span data-ttu-id="09020-109">Для числовых типов оператор `*` вычисляет результат двух операндов:</span><span class="sxs-lookup"><span data-stu-id="09020-109">For numeric types, the `*` operator computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a><span data-ttu-id="09020-110">Возможность перегрузки оператора</span><span class="sxs-lookup"><span data-stu-id="09020-110">Operator overloadability</span></span>

<span data-ttu-id="09020-111">Определяемые пользователем типы могут вызвать [перегрузку](../keywords/operator.md) бинарного оператора `*`.</span><span class="sxs-lookup"><span data-stu-id="09020-111">User-defined types can [overload](../keywords/operator.md) a binary `*` operator.</span></span> <span data-ttu-id="09020-112">При перегрузке бинарного оператора `*` неявно перегружается и соответствующий [оператор присваивания умножения](multiplication-assignment-operator.md) `*=`.</span><span class="sxs-lookup"><span data-stu-id="09020-112">When a binary `*` operator is overloaded, the [multiplication assignment operator](multiplication-assignment-operator.md) `*=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="09020-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="09020-113">C# language specification</span></span>

<span data-ttu-id="09020-114">См. дополнительные сведения об [операторе косвенного обращения к указателю](~/_csharplang/spec/unsafe-code.md#pointer-indirection) и [операторе умножения](~/_csharplang/spec/expressions.md#multiplication-operator) в [спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="09020-114">For more information, see the [Pointer indirection](~/_csharplang/spec/unsafe-code.md#pointer-indirection) and [Multiplication operator](~/_csharplang/spec/expressions.md#multiplication-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09020-115">См. также</span><span class="sxs-lookup"><span data-stu-id="09020-115">See also</span></span>

- [<span data-ttu-id="09020-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="09020-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="09020-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="09020-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="09020-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="09020-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="09020-119">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="09020-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)