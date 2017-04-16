---
title: "How to: Listen for Cancellation Requests That Have Wait Handles | Microsoft Docs"
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
  - "cancellation, waiting with wait handles"
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Listen for Cancellation Requests That Have Wait Handles
Если метод блокируется на время ожидания сигнала о событии, то он не может проверить значение токена отмены и своевременно ответить.  В первом примере показывается порядок устранения данной проблемы при работе с такими событиями, как <xref:System.Threading.ManualResetEvent?displayProperty=fullName>, которые изначально не поддерживают инфраструктуру универсальной отмены.  Во втором примере показывается более рациональный подход, в котором используется событие <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>, поддерживающее универсальную отмену.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и отображает сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической.  Можно нажать F5, чтобы продолжить выполнение с этой ошибки. См. поведение системы при обработке этого исключения в примерах ниже.  Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, необходимо снять флажок "Только мой код" в меню **Сервис, Параметры, Отладка, Общие**.  
  
## Пример  
 В следующем примере с помощью события <xref:System.Threading.ManualResetEvent> демонстрируется порядок разблокирования дескрипторов ожидания, не поддерживающих универсальную отмену.  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## Пример  
 В следующем примере с помощью события <xref:System.Threading.ManualResetEventSlim> демонстрируется порядок разблокирования примитивов взаимодействия, поддерживающих универсальную отмену.  Такой же подход можно использовать и для других простых примитивов взаимодействия, таких как <xref:System.Threading.Semaphore>`Slim` и <xref:System.Threading.CountdownEvent>.  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## См. также  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)