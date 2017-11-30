---
title: "Практическое руководство. Прослушивание нескольких запросов на отмену"
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
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a>Практическое руководство. Прослушивание нескольких запросов на отмену
В этом примере показано, как для ожидания передачи данных двумя токенами отмены одновременно, чтобы можно было отменить операцию, если любой из токенов запрашивает ее.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической. Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже. Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, снимите флажок «Только мой код» в разделе **Сервис, параметры, отладка, Общие**.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> метод используется для объединения двух токенов в один токен. Это позволяет токен должен быть передан методов, которые принимают в качестве аргумента токен отмены лишь один. В примере демонстрируется типичный сценарий, в котором метод должен учитывать как токен, переданный из вне класса и токен, созданный внутри класса.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Если связанный токен создает <xref:System.OperationCanceledException>, маркер, который передается на исключение является связанный токен, а не один из предшествующих токенов. Чтобы определить, какой из токенов был отменен, проверьте состояние предшествующих токенов напрямую.  
  
 В этом примере <xref:System.AggregateException> никогда не должны создаваться, но оно возникает из-за в реальных сценариях другие исключения, кроме <xref:System.OperationCanceledException> , возникающие из делегата задачи упаковываются в <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>См. также  
 [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md)
