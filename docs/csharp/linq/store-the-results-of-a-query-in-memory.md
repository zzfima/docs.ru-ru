---
title: Сохранение результатов запроса в памяти
description: Как сохранять результаты.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 66a7a95c74db4062e76c54d4339ccb7343f44067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "65633569"
---
# <a name="store-the-results-of-a-query-in-memory"></a>Сохранение результатов запроса в памяти

Запрос, по сути, является набором инструкций, на основании которых осуществляется извлечение и организация данных. Запросы выполняются медленно по мере выполнения запроса к каждому последующему элементу в результирующем наборе. При использовании `foreach` для итерации результатов элементы возвращаются как те, к которым был получен доступ. Чтобы оценить запрос и сохранить его результаты без выполнения цикла `foreach`, просто вызовите один из следующих методов для переменной запроса:

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 Рекомендуется при сохранении результатов запроса назначить возвращенный объект коллекции новой переменной, как показано в следующем примере.

## <a name="example"></a>Пример

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a>См. также раздел

- [LINQ](index.md)
