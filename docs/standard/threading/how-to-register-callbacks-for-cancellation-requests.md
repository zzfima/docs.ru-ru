---
title: "How to: Register Callbacks for Cancellation Requests | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cancellation, how to register callbacks"
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Register Callbacks for Cancellation Requests
В приведенном ниже примере показана процедура регистрации делегата, который будет вызываться при принятии свойством <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> значения true в результате вызова <xref:System.Threading.CancellationTokenSource.Cancel%2A> для объекта, который создал токен.  Этот прием используется для отмены асинхронных операций, в которых отсутствует встроенная поддержка унифицированной инфраструктуры отмены, а также для разблокирования методов, ожидающих завершения асинхронной операции.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической.  Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже.  Чтобы выполнение программы не прерывалось после первой ошибки в Visual Studio, снимите флажок "Только мой код" в меню **Сервис, Параметры, Отладка, Общие**.  
  
## Пример  
 В примере ниже метод <xref:System.Net.WebClient.CancelAsync%2A> регистрируется в качестве метода, вызываемого при запросе отмены с помощью токена отмены.  
  
 [!code-csharp[Conceptual.Cancellation.Callback#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs#1)]
 [!code-vb[Conceptual.Cancellation.Callback#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb#1)]  
  
 Если при регистрации обратного вызова отмена уже была зарегистрирована, то этот обратный вызов гарантированно будет вызван.  В этом случае метод <xref:System.Net.WebClient.CancelAsync%2A> не выполняет никаких действий \(при отсутствии выполняющихся асинхронных операций\), поэтому этот метод можно вызывать всегда.  
  
## См. также  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)