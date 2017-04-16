---
title: "How to: Listen for Multiple Cancellation Requests | Microsoft Docs"
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
  - "cancellation tokens, joining"
  - "LinkedTokenSource, how to"
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Listen for Multiple Cancellation Requests
В этом примере показывается порядок ожидания передачи данных двумя токенами отмены одновременно, чтобы можно было отменить операцию, если какой\-либо из токенов запрашивает ее.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и отображает сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической.  Можно нажать F5, чтобы продолжить выполнение с этой ошибки. См. поведение системы при обработке этого исключения в примерах ниже.  Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, необходимо снять флажок "Только мой код" в меню **Сервис, Параметры, Отладка, Общие**.  
  
## Пример  
 В следующем примере метод <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> используется для объединения двух токенов в один.  Это дает возможность передавать токен в методы, которые принимают в качестве аргумента только один токен отмены.  В примере показывается наиболее распространенный сценарий, в котором метод должен учитывать как токен, переданный в класс извне, так и токен, созданный в классе.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Если связанный токен создает исключение <xref:System.OperationCanceledException>, то в исключение передается связанный токен, а не один из предшествующих токенов.  Чтобы определить, какой из токенов был отменен, следует проверить состояние предшествующих токенов напрямую.  
  
 В этом примере никогда не должно выводиться исключение <xref:System.AggregateException>, однако оно возникает, поскольку в реальных сценариях любые другие исключения кроме <xref:System.OperationCanceledException>, возникающие из делегата задачи, заключены в исключении <xref:System.OperationCanceledException>.  
  
## См. также  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)