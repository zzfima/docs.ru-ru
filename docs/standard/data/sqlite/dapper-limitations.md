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
# <a name="dapper-limitations"></a>Ограничения Dapper

При использовании Microsoft. Data. SQLite с [Dapper](https://stackexchange.github.io/Dapper/)необходимо учитывать ряд ограничений.

## <a name="parameters"></a>Параметры

В именах параметров SQLite учитывается регистр. Убедитесь, что имена параметров, используемых в SQL, соответствуют регистру свойств анонимного объекта. Проблема [#18861](https://github.com/dotnet/efcore/issues/18861) улучшит этот процесс.

Dapper также предполагают, что параметры должны использовать префикс `@`. Другие префиксы не будут работать.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a>Типы данных

Dapper считывает значения с помощью индексатора Склитедатареадер. Тип возвращаемого значения этого индексатора — Object, то есть он будет возвращать только длинные, Double, строковые или байтовые []. Дополнительные сведения см. в разделе [типы данных](types.md). Dapper обрабатывает большинство преобразований между этими и другими примитивными типами. К сожалению, он не обрабатывает `DateTimeOffset`, `Guid`или `TimeSpan`. Создайте обработчики типов, если вы хотите использовать эти типы в результатах.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

Не забудьте добавить обработчики типов перед запросом.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a>См. также:

* [Типы данных](types.md)
* [Ограничения Async](async.md)
