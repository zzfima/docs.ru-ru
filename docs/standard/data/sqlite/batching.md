---
title: Пакетная обработка
ms.date: 12/13/2019
description: Узнайте, как выполнить пакет инструкций SQL в одной команде.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450312"
---
# <a name="batching"></a><span data-ttu-id="64fcf-103">Пакетная обработка</span><span class="sxs-lookup"><span data-stu-id="64fcf-103">Batching</span></span>

<span data-ttu-id="64fcf-104">SQLite изначально не поддерживает пакетную обработку инструкций SQL в одной команде.</span><span class="sxs-lookup"><span data-stu-id="64fcf-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="64fcf-105">Но поскольку нет сети, она не будет действительно помогать в производительности.</span><span class="sxs-lookup"><span data-stu-id="64fcf-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="64fcf-106">Однако Microsoft. Data. SQLite реализует пакетирование инструкций в качестве удобства, чтобы сделать его более похожим на другие поставщики ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="64fcf-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="64fcf-107">При вызове <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>операторы выполняются до первого, который возвращает результаты.</span><span class="sxs-lookup"><span data-stu-id="64fcf-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="64fcf-108">Вызов <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> возобновляет выполнение инструкций до следующего, который возвращает результаты или до конца пакета.</span><span class="sxs-lookup"><span data-stu-id="64fcf-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="64fcf-109">При вызове <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> или <xref:System.Data.Common.DbDataReader.Close%2A> выполняются все оставшиеся инструкции, которые не использовались `NextResult()`.</span><span class="sxs-lookup"><span data-stu-id="64fcf-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="64fcf-110">Если не удалить модуль чтения данных, метод завершения пытается выполнить оставшиеся инструкции, но все возникшие ошибки игнорируются.</span><span class="sxs-lookup"><span data-stu-id="64fcf-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="64fcf-111">Поэтому при использовании пакетов важно удалять `DbDataReader` объекты.</span><span class="sxs-lookup"><span data-stu-id="64fcf-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="64fcf-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="64fcf-112">See also</span></span>

* [<span data-ttu-id="64fcf-113">Инструкция INSERT</span><span class="sxs-lookup"><span data-stu-id="64fcf-113">Bulk Insert</span></span>](bulk-insert.md)
