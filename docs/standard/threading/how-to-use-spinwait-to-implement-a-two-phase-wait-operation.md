---
title: "How to: Use SpinWait to Implement a Two-Phase Wait Operation | Microsoft Docs"
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
  - "SpinWait, how to synchronize two-phase wait"
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Use SpinWait to Implement a Two-Phase Wait Operation
Следующий пример показывает, как использовать объект <xref:System.Threading.SpinWait?displayProperty=fullName> для реализации двухэтапной операции ожидания.  На первом этапе объект синхронизации, `Latch`, выполняет несколько циклов, проверяя, стала ли блокировка доступной.  На втором этапе, если блокировка становится доступной, метод `Wait` возвращает управление без использования события <xref:System.Threading.ManualResetEvent?displayProperty=fullName> для выполнения ожидания, в противном случае метод `Wait` выполняет операцию ожидания.  
  
## Пример  
 В этом примере показана самая базовая реализация примитива синхронизации кратковременной блокировки.  Эту структуру данных можно использовать, когда предполагается, что времена ожидания будут очень короткими.  Этот пример используется только в качестве демонстрации.  Если в программе требуется использование возможности, похожей на защелку \(Latch\), рассмотрите возможность использования типа <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Защелка использует объект <xref:System.Threading.SpinWait>, чтобы быть установленной до тех пор, пока следующий вызов `SpinOnce` не заставит <xref:System.Threading.SpinWait> получить временной интервал в потоке.  В этот момент защелка переключает свой контекст, вызывая <xref:System.Threading.WaitHandle.WaitOne%2A> для <xref:System.Threading.ManualResetEvent> и передавая оставшуюся часть значения времени ожидания.  
  
 Выходные данные журнала показывают, как часто кратковременная блокировка могла повысить производительность, устанавливая блокировку без использования <xref:System.Threading.ManualResetEvent>.  
  
## См. также  
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)