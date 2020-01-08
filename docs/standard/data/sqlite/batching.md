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
# <a name="batching"></a>Пакетная обработка

SQLite изначально не поддерживает пакетную обработку инструкций SQL в одной команде. Но поскольку нет сети, она не будет действительно помогать в производительности. Однако Microsoft. Data. SQLite реализует пакетирование инструкций в качестве удобства, чтобы сделать его более похожим на другие поставщики ADO.NET.

При вызове <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>операторы выполняются до первого, который возвращает результаты. Вызов <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> возобновляет выполнение инструкций до следующего, который возвращает результаты или до конца пакета. При вызове <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> или <xref:System.Data.Common.DbDataReader.Close%2A> выполняются все оставшиеся инструкции, которые не использовались `NextResult()`. Если не удалить модуль чтения данных, метод завершения пытается выполнить оставшиеся инструкции, но все возникшие ошибки игнорируются. Поэтому при использовании пакетов важно удалять `DbDataReader` объекты.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>См. также:

* [Инструкция INSERT](bulk-insert.md)
