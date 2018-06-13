---
title: Сохранение результатов запроса в памяти
description: Как сохранять результаты.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: c125d134d7c1db98363844c12fc8abd3faa9c868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279637"
---
# <a name="store-the-results-of-a-query-in-memory"></a>Сохранение результатов запроса в памяти

Запрос, по сути, является набором инструкций, на основании которых осуществляется извлечение и организация данных. Запросы выполняются медленно по мере выполнения запроса к каждому последующему элементу в результирующем наборе. При использовании `foreach` для итерации результатов элементы возвращаются как те, к которым был получен доступ. Чтобы оценить запрос и сохранить его результаты без выполнения цикла `foreach`, просто вызовите один из следующих методов для переменной запроса:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Рекомендуется при сохранении результатов запроса назначить возвращенный объект коллекции новой переменной, как показано в следующем примере.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  

## <a name="see-also"></a>См. также  
 [Выражения запросов LINQ](index.md)
