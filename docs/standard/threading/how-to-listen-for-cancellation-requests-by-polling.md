---
title: Практическое руководство. Прослушивание запросов на отмену посредством опросов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1794b47db87f636cc2ccdf2eecb9e7ca334ae659
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46585432"
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>Практическое руководство. Прослушивание запросов на отмену посредством опросов
В примере ниже показан один из способов для регулярного опроса маркера отмены из пользовательского кода, чтобы отслеживать запросы на отмену из вызывающего потока. Мы применили здесь тип <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, но вы можете использовать такой же подход и к асинхронным операциям, для которых прямо указан тип <xref:System.Threading.ThreadPool?displayProperty=nameWithType> или <xref:System.Threading.Thread?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 Опросы выполняются из циклического или рекурсивного кода, который может периодически считывать логическое значение свойства <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>. Если вы используете тип <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> и вызывающий поток ожидает, пока завершится задача, вы можете применить метод <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> для проверки свойства и создания исключений. Этот метод позволяет гарантировать, что в ответ на запрос создается правильное исключение. Если вы используете <xref:System.Threading.Tasks.Task>, то лучше вызвать этот метод, чем создать исключение <xref:System.OperationCanceledException> вручную. Если нет необходимости создавать исключение, вы можете просто проверить свойство и выполнить выход из метода, когда свойство получит значение `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 Вызов <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> выполняется крайне быстро и не повышает нагрузку на циклы.  
  
 При вызове <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> вам следует явным образом проверить свойство <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>, если при отмене нужно выполнять какие-то еще действия помимо создания исключения. В нашем примере код фактически обращается к свойству дважды: один раз явным образом и второй раз в методе <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>. Но так как при считывании свойства <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> используется только одна инструкция чтения из временного объекта для каждого доступа, двойной доступ не влияет на производительность существенным образом. Даже в этом случае вызов метода предпочтительнее, чем создание исключения <xref:System.OperationCanceledException> вручную.  
  
## <a name="see-also"></a>См. также

- [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md)
