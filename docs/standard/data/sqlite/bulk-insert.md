---
title: Инструкция INSERT
ms.date: 12/13/2019
description: Советы по повышению производительности, которые можно использовать при внесении многочисленных изменений в базу данных.
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450300"
---
# <a name="bulk-insert"></a><span data-ttu-id="81349-103">Инструкция INSERT</span><span class="sxs-lookup"><span data-stu-id="81349-103">Bulk insert</span></span>

<span data-ttu-id="81349-104">SQLite не имеет специального способа для выполнения операций вставки данных.</span><span class="sxs-lookup"><span data-stu-id="81349-104">SQLite doesn't have any special way to bulk insert data.</span></span> <span data-ttu-id="81349-105">Чтобы обеспечить оптимальную производительность при вставке или обновлении данных, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="81349-105">To get optimal performance when inserting or updating data, ensure that you do the following:</span></span>

- <span data-ttu-id="81349-106">Используйте транзакцию.</span><span class="sxs-lookup"><span data-stu-id="81349-106">Use a transaction.</span></span>
- <span data-ttu-id="81349-107">Повторно используйте ту же параметризованную команду.</span><span class="sxs-lookup"><span data-stu-id="81349-107">Reuse the same parameterized command.</span></span> <span data-ttu-id="81349-108">Последующие выполнения будут повторно использовать компиляцию первого из них.</span><span class="sxs-lookup"><span data-stu-id="81349-108">Subsequent executions will reuse the compilation of the first one.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
