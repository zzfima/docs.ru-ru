---
title: Ограничения Dapper
ms.date: 12/13/2019
description: Описание некоторых ограничений, которые будут возникать при использовании Dapper.
ms.openlocfilehash: 90c7fb24f068d663081390bdba9b1b222b4be56e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450498"
---
# <a name="dapper-limitations"></a><span data-ttu-id="9a973-103">Ограничения Dapper</span><span class="sxs-lookup"><span data-stu-id="9a973-103">Dapper limitations</span></span>

<span data-ttu-id="9a973-104">При использовании Microsoft. Data. SQLite с [Dapper](https://stackexchange.github.io/Dapper/)необходимо учитывать ряд ограничений.</span><span class="sxs-lookup"><span data-stu-id="9a973-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="9a973-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a973-105">Parameters</span></span>

<span data-ttu-id="9a973-106">В именах параметров SQLite учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="9a973-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="9a973-107">Убедитесь, что имена параметров, используемых в SQL, соответствуют регистру свойств анонимного объекта.</span><span class="sxs-lookup"><span data-stu-id="9a973-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="9a973-108">Проблема [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) улучшит этот процесс.</span><span class="sxs-lookup"><span data-stu-id="9a973-108">Issue [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="9a973-109">Dapper также предполагают, что параметры должны использовать префикс `@`.</span><span class="sxs-lookup"><span data-stu-id="9a973-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="9a973-110">Другие префиксы не будут работать.</span><span class="sxs-lookup"><span data-stu-id="9a973-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="9a973-111">Типы данных</span><span class="sxs-lookup"><span data-stu-id="9a973-111">Data types</span></span>

<span data-ttu-id="9a973-112">Dapper считывает значения с помощью индексатора Склитедатареадер.</span><span class="sxs-lookup"><span data-stu-id="9a973-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="9a973-113">Тип возвращаемого значения этого индексатора — Object, то есть он будет возвращать только длинные, Double, строковые или байтовые [].</span><span class="sxs-lookup"><span data-stu-id="9a973-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="9a973-114">Дополнительные сведения см. в разделе [типы данных](types.md).</span><span class="sxs-lookup"><span data-stu-id="9a973-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="9a973-115">Dapper обрабатывает большинство преобразований между этими и другими примитивными типами.</span><span class="sxs-lookup"><span data-stu-id="9a973-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="9a973-116">К сожалению, он не обрабатывает `DateTimeOffset`, `Guid`или `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="9a973-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="9a973-117">Создайте обработчики типов, если вы хотите использовать эти типы в результатах.</span><span class="sxs-lookup"><span data-stu-id="9a973-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="9a973-118">Не забудьте добавить обработчики типов перед запросом.</span><span class="sxs-lookup"><span data-stu-id="9a973-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="9a973-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a973-119">See also</span></span>

* [<span data-ttu-id="9a973-120">Типы данных</span><span class="sxs-lookup"><span data-stu-id="9a973-120">Data types</span></span>](types.md)
* [<span data-ttu-id="9a973-121">Ограничения Async</span><span class="sxs-lookup"><span data-stu-id="9a973-121">Async limitations</span></span>](async.md)
