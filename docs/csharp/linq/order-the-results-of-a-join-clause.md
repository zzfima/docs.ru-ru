---
title: Упорядочение результатов предложения соединения (LINQ в C#)
description: Узнайте, как упорядочивать результаты предложения соединения LINQ в C#.
ms.date: 12/01/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f60000b83bf378dd8740b7255d421dd4335614c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659869"
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="d5141-103">Упорядочение результатов предложения соединения</span><span class="sxs-lookup"><span data-stu-id="d5141-103">Order the results of a join clause</span></span>

<span data-ttu-id="d5141-104">В этом примере показано, как упорядочить результаты операции соединения.</span><span class="sxs-lookup"><span data-stu-id="d5141-104">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="d5141-105">Обратите внимание на то, что упорядочение выполняется после соединения.</span><span class="sxs-lookup"><span data-stu-id="d5141-105">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="d5141-106">Несмотря на то, что предложение `orderby` с одним или несколькими исходными последовательностями использовать до соединения можно, обычно это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="d5141-106">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="d5141-107">Некоторые поставщики LINQ могут не сохранять этот порядок после соединения.</span><span class="sxs-lookup"><span data-stu-id="d5141-107">Some LINQ providers might not preserve that ordering after the join.</span></span>

## <a name="example"></a><span data-ttu-id="d5141-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d5141-108">Example</span></span>

<span data-ttu-id="d5141-109">Этот запрос создает группу соединения, а затем сортирует группы по элементу категории, который остается в области действия.</span><span class="sxs-lookup"><span data-stu-id="d5141-109">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="d5141-110">В инициализаторе анонимного типа подзапрос упорядочивает все соответствующие элементы из последовательности продуктов.</span><span class="sxs-lookup"><span data-stu-id="d5141-110">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a><span data-ttu-id="d5141-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d5141-111">See also</span></span>

- [<span data-ttu-id="d5141-112">LINQ</span><span class="sxs-lookup"><span data-stu-id="d5141-112">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="d5141-113">предложение orderby</span><span class="sxs-lookup"><span data-stu-id="d5141-113">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="d5141-114">предложение join</span><span class="sxs-lookup"><span data-stu-id="d5141-114">join clause</span></span>](../language-reference/keywords/join-clause.md)
