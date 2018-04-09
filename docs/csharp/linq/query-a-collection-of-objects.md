---
title: Запрос коллекции объектов
description: Описывает, как запрашивать коллекции.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: a62e5c6324d15376f1b42ad078eeb883b05ef14f
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
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
