---
title: Логические операторы
description: Дополнительные сведения о логических операторов, которые доступны в F# языка программирования.
ms.date: 05/16/2016
ms.openlocfilehash: 5353b6ec6a0bd610f3446761a1d28f01f0403302
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925818"
---
# <a name="boolean-operators"></a><span data-ttu-id="cc0dc-103">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="cc0dc-103">Boolean Operators</span></span>

<span data-ttu-id="cc0dc-104">В этом разделе описывается поддержка логических операторов в F# языка.</span><span class="sxs-lookup"><span data-stu-id="cc0dc-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="cc0dc-105">Сводка по логические операторы</span><span class="sxs-lookup"><span data-stu-id="cc0dc-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="cc0dc-106">В следующей таблице перечислены логические операторы, доступные в F# языка.</span><span class="sxs-lookup"><span data-stu-id="cc0dc-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="cc0dc-107">Единственный тип, поддерживаемый эти операторы — `bool` типа.</span><span class="sxs-lookup"><span data-stu-id="cc0dc-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="cc0dc-108">Оператор</span><span class="sxs-lookup"><span data-stu-id="cc0dc-108">Operator</span></span>|<span data-ttu-id="cc0dc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cc0dc-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="cc0dc-110">Логическое отрицание</span><span class="sxs-lookup"><span data-stu-id="cc0dc-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="cc0dc-111">Логическое или</span><span class="sxs-lookup"><span data-stu-id="cc0dc-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="cc0dc-112">Логическое и</span><span class="sxs-lookup"><span data-stu-id="cc0dc-112">Boolean AND</span></span>|

<span data-ttu-id="cc0dc-113">Логические и и или операторы выполнения *сокращенным вычислением*, то есть они вычисляют выражение справа от оператора, только в том случае, когда это необходимо для определения результата выражения.</span><span class="sxs-lookup"><span data-stu-id="cc0dc-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="cc0dc-114">Второе выражение `&&` оператора определяется только в том случае, если первое выражение, результатом которого является `true`; второе выражение `||` оператора определяется только в том случае, если первое выражение, результатом которого является `false`.</span><span class="sxs-lookup"><span data-stu-id="cc0dc-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc0dc-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cc0dc-115">See also</span></span>

- [<span data-ttu-id="cc0dc-116">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="cc0dc-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="cc0dc-117">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="cc0dc-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="cc0dc-118">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="cc0dc-118">Symbol and Operator Reference</span></span>](index.md)