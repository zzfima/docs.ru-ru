---
title: Запрос коллекции объектов (LINQ в C#)
description: Узнайте, как выполнять запросы к коллекциям с помощью LINQ в C#.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 9b2f5dd09c540800e9a2498d48883357f58c0116
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659817"
---
# <a name="query-a-collection-of-objects"></a>Запрос коллекции объектов

В этом примере показано, как выполнить простой запрос к списку объектов `Student`. Каждый объект `Student` содержит некоторые основные сведения об учащемся, а также список, отражающий баллы, которые он набрал по результатам четырех экзаменов.  
  
Это приложение служит основой для многих других примеров в этом разделе, где используется тот же источник данных `students`.  
  
## <a name="example"></a>Пример

Следующий запрос возвращает список учащихся, набравших 90 баллов или больше на первом экзамене.  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
Этот запрос намеренно сделан простым, чтобы с ним можно было экспериментировать. Например, можно добавить в предложение `where` дополнительные условия или отсортировать результаты с помощью предложения `orderby`.  
  
## <a name="see-also"></a>См. также раздел

- [LINQ](index.md)
- [Интерполяция строк](../language-reference/tokens/interpolated.md)
