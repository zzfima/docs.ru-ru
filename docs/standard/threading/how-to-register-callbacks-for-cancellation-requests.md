---
title: "Практическое руководство. Регистрация обратных вызовов для запросов на отмену"
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
helpviewer_keywords: cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 85b15ed610d80958ac9d7e3762ac8ea7b781b8d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-register-callbacks-for-cancellation-requests"></a>Практическое руководство. Регистрация обратных вызовов для запросов на отмену
Приведенный ниже показано, как зарегистрировать делегат, который будет вызываться при <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> свойство принимает значение true, если из-за вызова <xref:System.Threading.CancellationTokenSource.Cancel%2A> в объекте, который создал токен. Этот прием используется для отмены асинхронных операций, в которых отсутствует встроенная поддержка унифицированной инфраструктуры отмены, а также для разблокирования методов, ожидающих завершения асинхронной операции.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической. Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже. Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, снимите флажок «Только мой код» в разделе **Сервис, параметры, отладка, Общие**.  
  
## <a name="example"></a>Пример  
 В примере ниже метод <xref:System.Net.WebClient.CancelAsync%2A> регистрируется в качестве метода, вызываемого при запросе отмены с помощью токена отмены.  
  
 [!code-csharp[Conceptual.Cancellation.Callback#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs#1)]
 [!code-vb[Conceptual.Cancellation.Callback#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb#1)]  
  
 Если при регистрации обратного вызова отмена уже была зарегистрирована, то этот обратный вызов гарантированно будет вызван. В этом случае метод <xref:System.Net.WebClient.CancelAsync%2A> не выполняет никаких действий (при отсутствии выполняющихся асинхронных операций), поэтому этот метод можно вызывать всегда.  
  
## <a name="see-also"></a>См. также  
 [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md)
