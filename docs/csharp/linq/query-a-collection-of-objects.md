---
title: Запрос коллекции объектов
description: Описывает, как запрашивать коллекции.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: c690da2ae59d2a9b34a5bd403bc54797c4e95fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282396"
---
# <a name="query-a-collection-of-objects"></a>Запрос коллекции объектов
В этом примере показано, как выполнить простой запрос к списку объектов `Student`. Каждый объект `Student` содержит некоторые основные сведения об учащемся, а также список, отражающий баллы, которые он набрал по результатам четырех экзаменов.  
  
 Это приложение служит основой для многих других примеров в этом разделе, где используется тот же источник данных `students`.  
  
## <a name="example"></a>Пример  
 Следующий запрос возвращает список учащихся, набравших 90 баллов или больше на первом экзамене.  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 Этот запрос намеренно сделан простым, чтобы с ним можно было экспериментировать. Например, можно добавить в предложение `where` дополнительные условия или отсортировать результаты с помощью предложения `orderby`.  
  

## <a name="see-also"></a>См. также  
 [Выражения запросов LINQ](index.md)  
 [Интерполяция строк](../language-reference/tokens/interpolated.md)
