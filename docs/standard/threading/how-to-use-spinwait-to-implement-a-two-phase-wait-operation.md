---
title: "Практическое руководство. Использование объекта SpinWait для реализации двухэтапной операции ожидания"
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>Практическое руководство. Использование объекта SpinWait для реализации двухэтапной операции ожидания
В следующем примере показано, как использовать <xref:System.Threading.SpinWait?displayProperty=nameWithType> объекта для реализации двухэтапной операции ожидания. На первом этапе объект синхронизации, `Latch`, выполняет несколько циклов, пока он проверяет, является ли блокировка станет доступным. На втором этапе, если блокировка не станет доступной то `Wait` метод возвращает без использования <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> для выполнения его ожидания; в противном случае `Wait` выполняет ожидание.  
  
## <a name="example"></a>Пример  
 В этом примере показана очень простая реализация синхронизации кратковременной блокировки примитивов. Эта структура данных можно использовать, когда предполагается, что времена ожидания будут очень короткими. Данный пример является исключительно для демонстрационных целей. Если требуются функциональные возможности типа кратковременной блокировки в приложении, рассмотрите возможность использования <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Защелка использует <xref:System.Threading.SpinWait> объекта, чтобы только до следующего вызова `SpinOnce` вызывает <xref:System.Threading.SpinWait> для временной интервал потока. На этом этапе кратковременная блокировка вызывает собственный переключение контекста, вызвав <xref:System.Threading.WaitHandle.WaitOne%2A> на <xref:System.Threading.ManualResetEvent> и передачи в оставшейся части значение времени ожидания.  
  
 Выходные данные журнала показывают, как часто кратковременная блокировка могла для повышения производительности путем запроса на блокировку без использования <xref:System.Threading.ManualResetEvent>.  
  
## <a name="see-also"></a>См. также  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
