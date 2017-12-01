---
title: "Практическое руководство. Прослушивание запросов на отмену, содержащих дескрипторы ожидания"
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
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a>Практическое руководство. Прослушивание запросов на отмену, содержащих дескрипторы ожидания
Если метод блокируется на время ожидания сигнала события, не может проверить значение токена отмены и своевременно ответить. Первый пример показано, как решить эту проблему, при работе с событиями, такие как <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> , не поддерживаются унифицированная инфраструктура отмены. Второй пример показывает более простой подход, который использует <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, который поддерживает универсальную отмену.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической. Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже. Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, снимите флажок «Только мой код» в разделе **Сервис, параметры, отладка, Общие**.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Threading.ManualResetEvent> для демонстрации разблокирования дескрипторов ожидания, не поддерживающих универсальную отмену.  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Threading.ManualResetEventSlim> для демонстрации разблокировать координации примитивы, которые поддерживают универсальную отмену. Тот же подход можно использовать с других простых примитивов взаимодействия, таких как <xref:System.Threading.Semaphore> `Slim` и <xref:System.Threading.CountdownEvent>.  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a>См. также  
 [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md)
