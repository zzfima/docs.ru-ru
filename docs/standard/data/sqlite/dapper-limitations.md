---
title: Ограничения Dapper
ms.date: 12/13/2019
description: Описание некоторых ограничений, которые будут возникать при использовании Dapper.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901201"
---
# <a name="dapper-limitations"></a><span data-ttu-id="46234-103">Ограничения Dapper</span><span class="sxs-lookup"><span data-stu-id="46234-103">Dapper limitations</span></span>

<span data-ttu-id="46234-104">При использовании Microsoft. Data. SQLite с [Dapper](https://stackexchange.github.io/Dapper/)необходимо учитывать ряд ограничений.</span><span class="sxs-lookup"><span data-stu-id="46234-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="46234-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46234-105">Parameters</span></span>

<span data-ttu-id="46234-106">В именах параметров SQLite учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="46234-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="46234-107">Убедитесь, что имена параметров, используемых в SQL, соответствуют регистру свойств анонимного объекта.</span><span class="sxs-lookup"><span data-stu-id="46234-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="46234-108">Проблема [#18861](https://github.com/dotnet/efcore/issues/18861) улучшит этот процесс.</span><span class="sxs-lookup"><span data-stu-id="46234-108">Issue [#18861](https://github.com/dotnet/efcore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="46234-109">Dapper также предполагают, что параметры должны использовать префикс `@`.</span><span class="sxs-lookup"><span data-stu-id="46234-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="46234-110">Другие префиксы не будут работать.</span><span class="sxs-lookup"><span data-stu-id="46234-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="46234-111">Типы данных</span><span class="sxs-lookup"><span data-stu-id="46234-111">Data types</span></span>

<span data-ttu-id="46234-112">Dapper считывает значения с помощью индексатора Склитедатареадер.</span><span class="sxs-lookup"><span data-stu-id="46234-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="46234-113">Тип возвращаемого значения этого индексатора — Object, то есть он будет возвращать только длинные, Double, строковые или байтовые [].</span><span class="sxs-lookup"><span data-stu-id="46234-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="46234-114">Дополнительные сведения см. в разделе [типы данных](types.md).</span><span class="sxs-lookup"><span data-stu-id="46234-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="46234-115">Dapper обрабатывает большинство преобразований между этими и другими примитивными типами.</span><span class="sxs-lookup"><span data-stu-id="46234-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="46234-116">К сожалению, он не обрабатывает `DateTimeOffset`, `Guid`или `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="46234-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="46234-117">Создайте обработчики типов, если вы хотите использовать эти типы в результатах.</span><span class="sxs-lookup"><span data-stu-id="46234-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="46234-118">Не забудьте добавить обработчики типов перед запросом.</span><span class="sxs-lookup"><span data-stu-id="46234-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="46234-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="46234-119">See also</span></span>

* [<span data-ttu-id="46234-120">Типы данных</span><span class="sxs-lookup"><span data-stu-id="46234-120">Data types</span></span>](types.md)
* [<span data-ttu-id="46234-121">Ограничения Async</span><span class="sxs-lookup"><span data-stu-id="46234-121">Async limitations</span></span>](async.md)
