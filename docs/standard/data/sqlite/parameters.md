---
title: Параметры
ms.date: 12/13/2019
description: Узнайте, как использовать параметры SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450426"
---
# <a name="parameters"></a><span data-ttu-id="b9ecc-103">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9ecc-103">Parameters</span></span>

<span data-ttu-id="b9ecc-104">Параметры используются для защиты от атак путем внедрения кода SQL.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="b9ecc-105">Вместо сцепления вводимых пользователем данных с инструкциями SQL используйте параметры, чтобы гарантировать, что входные данные всегда рассматриваются как литеральное значение и никогда не выполняются.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="b9ecc-106">В SQLite параметры обычно разрешены в любом месте, где допускается использование литерала в инструкциях SQL.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="b9ecc-107">Для параметров можно использовать префикс `:`, `@`или `$`.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="b9ecc-108">Сведения о том, как значения .NET сопоставляются со значениями SQLite, см. в разделе [типы данных](types.md) .</span><span class="sxs-lookup"><span data-stu-id="b9ecc-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="b9ecc-109">Усечение</span><span class="sxs-lookup"><span data-stu-id="b9ecc-109">Truncation</span></span>

<span data-ttu-id="b9ecc-110">Используйте свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> для усечения значений текста и больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="b9ecc-111">Альтернативные типы</span><span class="sxs-lookup"><span data-stu-id="b9ecc-111">Alternative types</span></span>

<span data-ttu-id="b9ecc-112">Иногда может потребоваться использовать альтернативный тип SQLite.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="b9ecc-113">Это можно сделать, задав свойство <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="b9ecc-114">Можно использовать следующие альтернативные сопоставления типов.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="b9ecc-115">Сопоставления по умолчанию см. в разделе [типы данных](types.md).</span><span class="sxs-lookup"><span data-stu-id="b9ecc-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="b9ecc-116">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="b9ecc-116">Value</span></span>          | <span data-ttu-id="b9ecc-117">склитетипе</span><span class="sxs-lookup"><span data-stu-id="b9ecc-117">SqliteType</span></span> | <span data-ttu-id="b9ecc-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="b9ecc-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="b9ecc-119">Char</span><span class="sxs-lookup"><span data-stu-id="b9ecc-119">Char</span></span>           | <span data-ttu-id="b9ecc-120">Целое число</span><span class="sxs-lookup"><span data-stu-id="b9ecc-120">Integer</span></span>    | <span data-ttu-id="b9ecc-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="b9ecc-121">UTF-16</span></span>           |
| <span data-ttu-id="b9ecc-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="b9ecc-122">DateTime</span></span>       | <span data-ttu-id="b9ecc-123">Real</span><span class="sxs-lookup"><span data-stu-id="b9ecc-123">Real</span></span>       | <span data-ttu-id="b9ecc-124">Значение юлианского дня</span><span class="sxs-lookup"><span data-stu-id="b9ecc-124">Julian day value</span></span> |
| <span data-ttu-id="b9ecc-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b9ecc-125">DateTimeOffset</span></span> | <span data-ttu-id="b9ecc-126">Real</span><span class="sxs-lookup"><span data-stu-id="b9ecc-126">Real</span></span>       | <span data-ttu-id="b9ecc-127">Значение юлианского дня</span><span class="sxs-lookup"><span data-stu-id="b9ecc-127">Julian day value</span></span> |
| <span data-ttu-id="b9ecc-128">Идентификатор GUID</span><span class="sxs-lookup"><span data-stu-id="b9ecc-128">Guid</span></span>           | <span data-ttu-id="b9ecc-129">Большой двоичный объект</span><span class="sxs-lookup"><span data-stu-id="b9ecc-129">Blob</span></span>       |                  |
| <span data-ttu-id="b9ecc-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="b9ecc-130">TimeSpan</span></span>       | <span data-ttu-id="b9ecc-131">Real</span><span class="sxs-lookup"><span data-stu-id="b9ecc-131">Real</span></span>       | <span data-ttu-id="b9ecc-132">В днях</span><span class="sxs-lookup"><span data-stu-id="b9ecc-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="b9ecc-133">Параметры вывода</span><span class="sxs-lookup"><span data-stu-id="b9ecc-133">Output parameters</span></span>

<span data-ttu-id="b9ecc-134">SQLite не поддерживает выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="b9ecc-135">Вместо этого возвращаются значения в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="b9ecc-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9ecc-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="b9ecc-136">See also</span></span>

* [<span data-ttu-id="b9ecc-137">Типы данных</span><span class="sxs-lookup"><span data-stu-id="b9ecc-137">Data types</span></span>](types.md)
