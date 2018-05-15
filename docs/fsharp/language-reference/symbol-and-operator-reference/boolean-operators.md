---
title: Логические операторы (F#)
description: 'Дополнительные сведения о логических операторов, которые доступны в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: f8516ceb531907400f98dc4226d2985d3119e9e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="boolean-operators"></a><span data-ttu-id="2a68a-103">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="2a68a-103">Boolean Operators</span></span>

<span data-ttu-id="2a68a-104">В этом разделе описывается поддержка логических операторов в языке F #.</span><span class="sxs-lookup"><span data-stu-id="2a68a-104">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="2a68a-105">Сводка по логическим операторам</span><span class="sxs-lookup"><span data-stu-id="2a68a-105">Summary of Boolean Operators</span></span>
<span data-ttu-id="2a68a-106">В следующей таблице перечислены логические операторы, доступные в языке F #.</span><span class="sxs-lookup"><span data-stu-id="2a68a-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="2a68a-107">Эти операторы поддерживают только тип `bool` типа.</span><span class="sxs-lookup"><span data-stu-id="2a68a-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="2a68a-108">Оператор</span><span class="sxs-lookup"><span data-stu-id="2a68a-108">Operator</span></span>|<span data-ttu-id="2a68a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2a68a-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="2a68a-110">Логическое отрицание</span><span class="sxs-lookup"><span data-stu-id="2a68a-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="2a68a-111">Логическое или</span><span class="sxs-lookup"><span data-stu-id="2a68a-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="2a68a-112">Логическое и</span><span class="sxs-lookup"><span data-stu-id="2a68a-112">Boolean AND</span></span>|

<span data-ttu-id="2a68a-113">Логические и и или операторы выполнения *сокращенное вычисление*, то есть они вычисляют выражение справа от оператора, только в том случае, если это необходимо для определения результата выражения.</span><span class="sxs-lookup"><span data-stu-id="2a68a-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="2a68a-114">Второе выражение `&&` оператор выполняется только в том случае, если первое выражение, результатом которого является `true`; второе выражение `||` оператор выполняется только в том случае, если первое выражение, результатом которого является `false`.</span><span class="sxs-lookup"><span data-stu-id="2a68a-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a68a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2a68a-115">See Also</span></span>
[<span data-ttu-id="2a68a-116">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="2a68a-116">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="2a68a-117">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="2a68a-117">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="2a68a-118">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="2a68a-118">Symbol and Operator Reference</span></span>](index.md)
