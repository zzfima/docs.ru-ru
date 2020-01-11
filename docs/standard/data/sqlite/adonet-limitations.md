---
title: Ограничения ADO.NET
ms.date: 12/13/2019
description: Описание некоторых ограничений ADO.NET, которые могут возникнуть.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901255"
---
# <a name="adonet-limitations"></a><span data-ttu-id="1ebf7-103">Ограничения ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1ebf7-103">ADO.NET limitations</span></span>

<span data-ttu-id="1ebf7-104">Microsoft. Data. SQLite предоставляет реализации многих абстракций ADO.NET, но существуют некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="1ebf7-105">Сведения о схеме базы данных</span><span class="sxs-lookup"><span data-stu-id="1ebf7-105">Database schema information</span></span>

<span data-ttu-id="1ebf7-106">Метаданные о результатах запроса доступны с помощью метода <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="1ebf7-107">`DbConnection.GetSchema()` не реализована.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="1ebf7-108">Этот API не определен правильно, поэтому мы рекомендуем получать метаданные базы данных непосредственно с помощью стандартных API-интерфейсов SQLite, таких как таблица [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) и директива pragma [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) .</span><span class="sxs-lookup"><span data-stu-id="1ebf7-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="1ebf7-109">Дополнительные сведения см. в разделе [метаданные](metadata.md).</span><span class="sxs-lookup"><span data-stu-id="1ebf7-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="1ebf7-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="1ebf7-110">System.Transactions</span></span>

<span data-ttu-id="1ebf7-111">Microsoft. Data. SQLite пока еще не поддерживает System. Transactions.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="1ebf7-112">Вместо этого используйте транзакции ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="1ebf7-113">Дополнительные сведения см. в разделе [Transactions](transactions.md).</span><span class="sxs-lookup"><span data-stu-id="1ebf7-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="1ebf7-114">Предоставьте отзыв о нехватке поддержки для System. Transactions в [#13825](https://github.com/dotnet/efcore/issues/13825)выпуска.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/dotnet/efcore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="1ebf7-115">Адаптеры данных</span><span class="sxs-lookup"><span data-stu-id="1ebf7-115">Data adapters</span></span>

<span data-ttu-id="1ebf7-116">`DbDataAdapter` еще не реализована Microsoft. Data. SQLite.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="1ebf7-117">Это означает, что вы можете использовать только ADO.NET `DataSet` и `DataTable` для загрузки данных и не обновлять их.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="1ebf7-118">Чтобы оставить отзыв о реализации `DbDataAdapter`, используйте [#13838](https://github.com/dotnet/efcore/issues/13838) выпуска.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-118">Use issue [#13838](https://github.com/dotnet/efcore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="1ebf7-119">Параметры вывода</span><span class="sxs-lookup"><span data-stu-id="1ebf7-119">Output parameters</span></span>

<span data-ttu-id="1ebf7-120">SQLite не поддерживает выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="1ebf7-121">Позиционные параметры</span><span class="sxs-lookup"><span data-stu-id="1ebf7-121">Positional parameters</span></span>

<span data-ttu-id="1ebf7-122">Microsoft. Data. SQLite поддерживает только именованные [Параметры](parameters.md).</span><span class="sxs-lookup"><span data-stu-id="1ebf7-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="1ebf7-123">Позиционированные параметры не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="1ebf7-124">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="1ebf7-124">Stored procedures</span></span>

<span data-ttu-id="1ebf7-125">SQLite не поддерживает хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="1ebf7-126">Уровни изоляции</span><span class="sxs-lookup"><span data-stu-id="1ebf7-126">Isolation levels</span></span>

<span data-ttu-id="1ebf7-127">Уровни изоляции `Chaos` и `Snapshot` не поддерживаются в транзакциях SQLite.</span><span class="sxs-lookup"><span data-stu-id="1ebf7-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ebf7-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ebf7-128">See also</span></span>

* [<span data-ttu-id="1ebf7-129">Ограничения Async</span><span class="sxs-lookup"><span data-stu-id="1ebf7-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="1ebf7-130">Типы данных</span><span class="sxs-lookup"><span data-stu-id="1ebf7-130">Data types</span></span>](types.md)
* [<span data-ttu-id="1ebf7-131">Tранзакции</span><span class="sxs-lookup"><span data-stu-id="1ebf7-131">Transactions</span></span>](transactions.md)
