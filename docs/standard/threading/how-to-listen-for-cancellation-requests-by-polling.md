---
title: "Практическое руководство. Прослушивание запросов на отмену посредством опросов"
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>Практическое руководство. Прослушивание запросов на отмену посредством опросов
В следующем примере показано одним из способов пользовательский код может выполнять опрос токена отмены через регулярные интервалы, чтобы увидеть, есть ли запрос на отмену из вызывающего потока. В этом примере используется <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> типа, но тот же принцип применяется к асинхронных операций, которые созданы напрямую с помощью <xref:System.Threading.ThreadPool?displayProperty=nameWithType> типа или <xref:System.Threading.Thread?displayProperty=nameWithType> типа.  
  
## <a name="example"></a>Пример  
 Опроса необходим циклический или рекурсивный код, который может периодически считывать значение логического <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> свойство. Если вы используете <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> типа и ожидается для задачи завершения в вызывающем потоке, можно использовать <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> метода проверьте свойство, и выдается исключение. При использовании этого метода убедитесь, что правильно исключение вызывается в ответ на запрос. Если вы используете <xref:System.Threading.Tasks.Task>, то вызов этого метода лучше, чем вручную вызов <xref:System.OperationCanceledException>. Если нет необходимости создавать исключение, то можно просто проверить свойство и возврата из метода, если свойство `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 Вызов <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> выполняется очень быстро и не вносит в циклы существенную нагрузку.  
  
 При вызове <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, необходимо явно проверить <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> свойства, если у вас есть другие типы работ, действие в ответ на отмену, помимо создания исключения. В этом примере видно, что код фактически обращается к свойству дважды: один раз в явный доступ и снова <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> метод. Но поскольку в действии по считыванию <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> свойство используется только одна временная, инструкция чтения для каждого доступа, двойной доступ не важен с точки зрения производительности. По-прежнему рекомендуется, чтобы вызвать метод, не вызывая вручную <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>См. также  
 [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md)
