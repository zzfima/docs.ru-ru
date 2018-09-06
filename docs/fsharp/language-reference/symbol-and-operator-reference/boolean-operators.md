---
title: Логические операторы (F#)
description: 'Дополнительные сведения о логические операторы, доступные в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784518"
---
# <a name="boolean-operators"></a><span data-ttu-id="cfe56-103">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="cfe56-103">Boolean Operators</span></span>

<span data-ttu-id="cfe56-104">В этом разделе описывается поддержка логических операторов в языке F #.</span><span class="sxs-lookup"><span data-stu-id="cfe56-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="cfe56-105">Сводка по логические операторы</span><span class="sxs-lookup"><span data-stu-id="cfe56-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="cfe56-106">В следующей таблице перечислены логические операторы, доступные в языке F #.</span><span class="sxs-lookup"><span data-stu-id="cfe56-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="cfe56-107">Единственный тип, поддерживаемый эти операторы — `bool` типа.</span><span class="sxs-lookup"><span data-stu-id="cfe56-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="cfe56-108">Оператор</span><span class="sxs-lookup"><span data-stu-id="cfe56-108">Operator</span></span>|<span data-ttu-id="cfe56-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cfe56-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="cfe56-110">Логическое отрицание</span><span class="sxs-lookup"><span data-stu-id="cfe56-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="cfe56-111">Логическое или</span><span class="sxs-lookup"><span data-stu-id="cfe56-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="cfe56-112">Логическое и</span><span class="sxs-lookup"><span data-stu-id="cfe56-112">Boolean AND</span></span>|

<span data-ttu-id="cfe56-113">Логические и и или операторы выполнения *сокращенным вычислением*, то есть они вычисляют выражение справа от оператора, только в том случае, когда это необходимо для определения результата выражения.</span><span class="sxs-lookup"><span data-stu-id="cfe56-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="cfe56-114">Второе выражение `&&` оператора определяется только в том случае, если первое выражение, результатом которого является `true`; второе выражение `||` оператора определяется только в том случае, если первое выражение, результатом которого является `false`.</span><span class="sxs-lookup"><span data-stu-id="cfe56-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfe56-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cfe56-115">See also</span></span>

- [<span data-ttu-id="cfe56-116">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="cfe56-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="cfe56-117">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="cfe56-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="cfe56-118">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="cfe56-118">Symbol and Operator Reference</span></span>](index.md)
