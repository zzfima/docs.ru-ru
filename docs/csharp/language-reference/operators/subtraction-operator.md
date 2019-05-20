---
title: '- Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 920981addd5c779c9ad1c666ef45e1de5cd23408
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633005"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="847f9-102">Справочник по C#. Оператор -</span><span class="sxs-lookup"><span data-stu-id="847f9-102">- operator (C# Reference)</span></span>

<span data-ttu-id="847f9-103">Оператор `-` может функционировать как унарный или как бинарный оператор.</span><span class="sxs-lookup"><span data-stu-id="847f9-103">The `-` operator can function as either a unary or a binary operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="847f9-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="847f9-104">Remarks</span></span>

<span data-ttu-id="847f9-105">Унарные операторы `-` предварительно определены для всех числовых типов.</span><span class="sxs-lookup"><span data-stu-id="847f9-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="847f9-106">Результатом использования унарного оператора `-` для числового типа является числовое отрицание операнда.</span><span class="sxs-lookup"><span data-stu-id="847f9-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>

<span data-ttu-id="847f9-107">Бинарные операторы `-`, предопределенные для всех числовых типов и типов перечисления, обеспечивают вычитание второго операнда из первого.</span><span class="sxs-lookup"><span data-stu-id="847f9-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>

<span data-ttu-id="847f9-108">Для типов делегатов также используется бинарный оператор `-`, который выполняет удаление делегатов.</span><span class="sxs-lookup"><span data-stu-id="847f9-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>

<span data-ttu-id="847f9-109">Пользовательские типы могут перегружать унарный оператор `-` и бинарный оператор `-`.</span><span class="sxs-lookup"><span data-stu-id="847f9-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="847f9-110">См. дополнительные о [ключевом слове operator](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="847f9-110">For more information, see [operator keyword](../keywords/operator.md).</span></span>

## <a name="example"></a><span data-ttu-id="847f9-111">Пример</span><span class="sxs-lookup"><span data-stu-id="847f9-111">Example</span></span>

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a><span data-ttu-id="847f9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="847f9-112">See also</span></span>

- [<span data-ttu-id="847f9-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="847f9-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="847f9-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="847f9-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="847f9-115">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="847f9-115">C# operators</span></span>](index.md)
