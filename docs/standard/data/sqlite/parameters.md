---
title: Параметры
ms.date: 12/13/2019
description: Узнайте, как использовать параметры S'L.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401205"
---
# <a name="parameters"></a><span data-ttu-id="34f5b-103">Параметры</span><span class="sxs-lookup"><span data-stu-id="34f5b-103">Parameters</span></span>

<span data-ttu-id="34f5b-104">Параметры используются для защиты от атак на впрыски с Помощью СЗЛ.</span><span class="sxs-lookup"><span data-stu-id="34f5b-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="34f5b-105">Вместо того, чтобы совмещать пользовательский ввод с операторами S'L, используйте параметры, чтобы гарантировать, что входные данные только когда-либо рассматриваются как буквальное значение и никогда не выполняются.</span><span class="sxs-lookup"><span data-stu-id="34f5b-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="34f5b-106">В S'Lite параметры, как правило, допускаются в любом месте, буквальные допустимые в заявлениях S'L.</span><span class="sxs-lookup"><span data-stu-id="34f5b-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="34f5b-107">Параметры могут быть префиксированы либо `:`, `@`или `$`.</span><span class="sxs-lookup"><span data-stu-id="34f5b-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="34f5b-108">Прослеживать [типы данных](types.md) для получения подробной информации о том, как значения .NET отображаются с значениями S'Lite.</span><span class="sxs-lookup"><span data-stu-id="34f5b-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="34f5b-109">Усечение</span><span class="sxs-lookup"><span data-stu-id="34f5b-109">Truncation</span></span>

<span data-ttu-id="34f5b-110">Используйте <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> свойство для усечения значений TEXT и BLOB.</span><span class="sxs-lookup"><span data-stu-id="34f5b-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="34f5b-111">Альтернативные типы</span><span class="sxs-lookup"><span data-stu-id="34f5b-111">Alternative types</span></span>

<span data-ttu-id="34f5b-112">Иногда можно использовать альтернативный тип S'Lite.</span><span class="sxs-lookup"><span data-stu-id="34f5b-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="34f5b-113">Сделайте это, <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> установив свойство.</span><span class="sxs-lookup"><span data-stu-id="34f5b-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="34f5b-114">Можно использовать следующие отображения альтернативного типа.</span><span class="sxs-lookup"><span data-stu-id="34f5b-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="34f5b-115">Для карт по умолчанию [см.](types.md)</span><span class="sxs-lookup"><span data-stu-id="34f5b-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="34f5b-116">Значение</span><span class="sxs-lookup"><span data-stu-id="34f5b-116">Value</span></span>          | <span data-ttu-id="34f5b-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="34f5b-117">SqliteType</span></span> | <span data-ttu-id="34f5b-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="34f5b-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="34f5b-119">CHAR</span><span class="sxs-lookup"><span data-stu-id="34f5b-119">Char</span></span>           | <span data-ttu-id="34f5b-120">Целое число</span><span class="sxs-lookup"><span data-stu-id="34f5b-120">Integer</span></span>    | <span data-ttu-id="34f5b-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="34f5b-121">UTF-16</span></span>           |
| <span data-ttu-id="34f5b-122">Дата и время</span><span class="sxs-lookup"><span data-stu-id="34f5b-122">DateTime</span></span>       | <span data-ttu-id="34f5b-123">Real</span><span class="sxs-lookup"><span data-stu-id="34f5b-123">Real</span></span>       | <span data-ttu-id="34f5b-124">Джулиан день значение</span><span class="sxs-lookup"><span data-stu-id="34f5b-124">Julian day value</span></span> |
| <span data-ttu-id="34f5b-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="34f5b-125">DateTimeOffset</span></span> | <span data-ttu-id="34f5b-126">Real</span><span class="sxs-lookup"><span data-stu-id="34f5b-126">Real</span></span>       | <span data-ttu-id="34f5b-127">Джулиан день значение</span><span class="sxs-lookup"><span data-stu-id="34f5b-127">Julian day value</span></span> |
| <span data-ttu-id="34f5b-128">Guid</span><span class="sxs-lookup"><span data-stu-id="34f5b-128">Guid</span></span>           | <span data-ttu-id="34f5b-129">BLOB-объект</span><span class="sxs-lookup"><span data-stu-id="34f5b-129">Blob</span></span>       |                  |
| <span data-ttu-id="34f5b-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="34f5b-130">TimeSpan</span></span>       | <span data-ttu-id="34f5b-131">Real</span><span class="sxs-lookup"><span data-stu-id="34f5b-131">Real</span></span>       | <span data-ttu-id="34f5b-132">В дни</span><span class="sxs-lookup"><span data-stu-id="34f5b-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="34f5b-133">Параметры вывода</span><span class="sxs-lookup"><span data-stu-id="34f5b-133">Output parameters</span></span>

<span data-ttu-id="34f5b-134">S'Lite не поддерживает параметры вывода.</span><span class="sxs-lookup"><span data-stu-id="34f5b-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="34f5b-135">Вместо этого значения возврата в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="34f5b-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="34f5b-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="34f5b-136">See also</span></span>

* [<span data-ttu-id="34f5b-137">Типы данных</span><span class="sxs-lookup"><span data-stu-id="34f5b-137">Data types</span></span>](types.md)
