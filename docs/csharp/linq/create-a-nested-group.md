---
title: Создание вложенной группы (LINQ в C#)
description: Узнайте, как создать вложенную группу в выражении запроса LINQ в C#.
ms.date: 12/01/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 7d056c9e215ccc7ca24d621b64e2328bed79f22e
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857675"
---
# <a name="create-a-nested-group"></a><span data-ttu-id="57fa2-103">Создание вложенной группы</span><span class="sxs-lookup"><span data-stu-id="57fa2-103">Create a nested group</span></span>

<span data-ttu-id="57fa2-104">В следующем примере демонстрируется создание вложенных групп в выражении запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="57fa2-104">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="57fa2-105">Каждая группа, созданная в соответствии с годом обучения или курсом учащегося, затем подразделяется на группы по именам учащихся.</span><span class="sxs-lookup"><span data-stu-id="57fa2-105">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>

## <a name="example"></a><span data-ttu-id="57fa2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="57fa2-106">Example</span></span>

> [!NOTE]
> <span data-ttu-id="57fa2-107">Этот пример содержит ссылки на объекты, определенные в примере кода в разделе [Запрос коллекции объектов](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="57fa2-107">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

<span data-ttu-id="57fa2-108">Обратите внимание, что для выполнения итерации по внутренним элементам вложенной группы необходимо три вложенных цикла `foreach`.</span><span class="sxs-lookup"><span data-stu-id="57fa2-108">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>

## <a name="see-also"></a><span data-ttu-id="57fa2-109">См. также</span><span class="sxs-lookup"><span data-stu-id="57fa2-109">See also</span></span>

- [<span data-ttu-id="57fa2-110">LINQ</span><span class="sxs-lookup"><span data-stu-id="57fa2-110">Language Integrated Query (LINQ)</span></span>](index.md)
