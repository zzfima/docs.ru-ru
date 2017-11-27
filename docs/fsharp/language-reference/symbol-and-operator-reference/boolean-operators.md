---
title: "Логические операторы (F#)"
description: "Дополнительные сведения о логических операторов, которые доступны в языке F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="boolean-operators"></a><span data-ttu-id="fb63d-104">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="fb63d-104">Boolean Operators</span></span>

<span data-ttu-id="fb63d-105">В этом разделе описывается поддержка логических операторов в языке F #.</span><span class="sxs-lookup"><span data-stu-id="fb63d-105">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="fb63d-106">Сводка по логическим операторам</span><span class="sxs-lookup"><span data-stu-id="fb63d-106">Summary of Boolean Operators</span></span>
<span data-ttu-id="fb63d-107">В следующей таблице перечислены логические операторы, доступные в языке F #.</span><span class="sxs-lookup"><span data-stu-id="fb63d-107">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="fb63d-108">Эти операторы поддерживают только тип `bool` типа.</span><span class="sxs-lookup"><span data-stu-id="fb63d-108">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="fb63d-109">Оператор</span><span class="sxs-lookup"><span data-stu-id="fb63d-109">Operator</span></span>|<span data-ttu-id="fb63d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="fb63d-110">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="fb63d-111">Логическое отрицание</span><span class="sxs-lookup"><span data-stu-id="fb63d-111">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="fb63d-112">Логическое или</span><span class="sxs-lookup"><span data-stu-id="fb63d-112">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="fb63d-113">Логическое и</span><span class="sxs-lookup"><span data-stu-id="fb63d-113">Boolean AND</span></span>|

<span data-ttu-id="fb63d-114">Логические и и или операторы выполнения *сокращенное вычисление*, то есть они вычисляют выражение справа от оператора, только в том случае, если это необходимо для определения результата выражения.</span><span class="sxs-lookup"><span data-stu-id="fb63d-114">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="fb63d-115">Второе выражение `&&` оператор выполняется только в том случае, если первое выражение, результатом которого является `true`; второе выражение `||` оператор выполняется только в том случае, если первое выражение, результатом которого является `false`.</span><span class="sxs-lookup"><span data-stu-id="fb63d-115">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb63d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="fb63d-116">See Also</span></span>
[<span data-ttu-id="fb63d-117">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="fb63d-117">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="fb63d-118">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="fb63d-118">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="fb63d-119">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="fb63d-119">Symbol and Operator Reference</span></span>](index.md)
