---
title: Логические операторы (F#)
description: Дополнительные сведения о логические операторы, доступные в языке F#.
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "45638484"
---
# <a name="boolean-operators"></a><span data-ttu-id="8c8f4-103">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="8c8f4-103">Boolean Operators</span></span>

<span data-ttu-id="8c8f4-104">В этом разделе описывается поддержка логических операторов в языке F#.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="8c8f4-105">Сводка по логические операторы</span><span class="sxs-lookup"><span data-stu-id="8c8f4-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="8c8f4-106">В следующей таблице перечислены логические операторы, доступные в языке F#.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="8c8f4-107">Единственный тип, поддерживаемый эти операторы — `bool` типа.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="8c8f4-108">Оператор</span><span class="sxs-lookup"><span data-stu-id="8c8f4-108">Operator</span></span>|<span data-ttu-id="8c8f4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8c8f4-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="8c8f4-110">Логическое отрицание</span><span class="sxs-lookup"><span data-stu-id="8c8f4-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="8c8f4-111">Логическое или</span><span class="sxs-lookup"><span data-stu-id="8c8f4-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="8c8f4-112">Логическое и</span><span class="sxs-lookup"><span data-stu-id="8c8f4-112">Boolean AND</span></span>|

<span data-ttu-id="8c8f4-113">Логические и и или операторы выполнения *сокращенным вычислением*, то есть они вычисляют выражение справа от оператора, только в том случае, когда это необходимо для определения результата выражения.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="8c8f4-114">Второе выражение `&&` оператора определяется только в том случае, если первое выражение, результатом которого является `true`; второе выражение `||` оператора определяется только в том случае, если первое выражение, результатом которого является `false`.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c8f4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8c8f4-115">See also</span></span>

- [<span data-ttu-id="8c8f4-116">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="8c8f4-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="8c8f4-117">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="8c8f4-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="8c8f4-118">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="8c8f4-118">Symbol and Operator Reference</span></span>](index.md)
