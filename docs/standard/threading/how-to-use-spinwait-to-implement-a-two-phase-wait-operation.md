---
title: Практическое руководство. Использование объекта SpinWait для реализации двухэтапной операции ожидания
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dcb2fbf5e0a310156fdc6fac5fe736692e8ec133
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44209216"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>Практическое руководство. Использование объекта SpinWait для реализации двухэтапной операции ожидания
В примере ниже показано, как использовать объект <xref:System.Threading.SpinWait?displayProperty=nameWithType> для реализации двухэтапной операции ожидания. На первом этапе объект синхронизации `Latch` выполняет несколько циклов, в которых проверяет доступность блокировки. На втором этапе, если блокировка стала доступной, метод `Wait` возвращается, не вызывая <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> для ожидания. В противном случае `Wait` выполняет операцию ожидания.  
  
## <a name="example"></a>Пример  
 Этот пример содержит простейшую реализацию примитива синхронизации с кратковременной блокировкой. Вы можете применить такую структуру данных, если время ожидания должно быть очень коротким. Этот пример приведен только в качестве демонстрации. Если для вашей программы нужна функция кратковременной блокировки, мы рекомендуем применить <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Кратковременная блокировка использует объект <xref:System.Threading.SpinWait>, чтобы оставаться в цикле ожидания, пока очередной вызов `SpinOnce` не вынудит <xref:System.Threading.SpinWait> приостановить процесс и освободить временной интервал потока. В этот момент кратковременная блокировка осуществляет переключение контекста, вызвав <xref:System.Threading.WaitHandle.WaitOne%2A> для <xref:System.Threading.ManualResetEvent>, которому передает значение оставшегося времени ожидания.  
  
 Выходные данные журнала позволят понять, как часто кратковременная блокировка позволяет повысить производительность, реализуя блокировку без использования <xref:System.Threading.ManualResetEvent>.  
  
## <a name="see-also"></a>См. также

- [SpinWait](../../../docs/standard/threading/spinwait.md)  
- [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
