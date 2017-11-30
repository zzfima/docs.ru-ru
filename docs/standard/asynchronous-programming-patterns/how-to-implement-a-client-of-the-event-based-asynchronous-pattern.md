---
title: "Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>Практическое руководство. Реализация клиента асинхронной модели, основанной на событиях
В следующем примере кода показано, как использовать компонент, который соответствует [Обзор асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md). В форме, в этом примере используется `PrimeNumberCalculator` компонента, описываемые в [как: реализация компонента, поддерживающего асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 При запуске проекта, использующего в этом примере вы увидите «Calculator простых чисел» формы с сеткой и две кнопки: **новая задача** и **отменить**. Можно щелкнуть **новая задача** несколько раз подряд, и для каждого нажатия асинхронной операции начинается вычисление, чтобы определить, является ли число случайным образом созданный тест простым. В форме будет периодически отображаться ход выполнения и добавочных результатов. Каждой операции присвоен уникальный идентификатор задачи. Результат вычисления отображается в **результат** столбца; Если проверяемое число не является простым, оно помечается как **составной,** и отображается первый делитель.  
  
 Все ожидающие операции может быть отменена с **отменить** кнопки. Можно сделать выбор нескольких элементов.  
  
> [!NOTE]
>  Большинство чисел не будут простыми. Если после нескольких завершенных операций не найдены простых чисел, просто запустите дополнительные задачи, и в итоге вы найдете некоторые простые числа.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
