---
title: "Запрос коллекции объектов"
description: "Описывает, как запрашивать коллекции."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 74d6c1f080c3e70867f5d2f074315bd1d8486bf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 [Интерполированные строки](../language-reference/keywords/interpolated-strings.md)
