---
title: SpinWait
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
helpviewer_keywords: synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfaf85c0fe1de3be89618ae540e9c183b66a11eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="spinwait"></a>SpinWait
<xref:System.Threading.SpinWait?displayProperty=nameWithType>— Тип упрощенной синхронизации, который можно использовать в низкоуровневых сценариях, чтобы избежать ресурсоемких переключений контекста и переходов в режим ядра, необходимых для событий ядра. На многоядерных компьютерах при ресурса не ожидается держаться в течение длительного времени, может быть более эффективным ожидающий поток запустить в пользовательском режиме несколько десятков или сотен циклов и повторная попытка получения ресурса. Если ресурс доступен после выхода из цикла, можно сэкономить несколько тысяч тактов процессора. Если ресурс недоступен по-прежнему, вы потратили только несколько циклов и по-прежнему можете ввести ожидания на основе ядра. Это сочетание цикл последующим ожиданием, иногда называют *двухэтапной операции ожидания*.  
  
 <xref:System.Threading.SpinWait>предназначены для использования в сочетании с типами .NET Framework, которые являются оболочкой событий ядра, такие как <xref:System.Threading.ManualResetEvent>. <xref:System.Threading.SpinWait>может также использоваться сама по себе для базовых функций цикла в одной программе.  
  
 <xref:System.Threading.SpinWait>Это не просто пустой цикл. Он аккуратно реализован, чтобы обеспечить правильное циклическое поведение в общем случае, и сам будет инициировать переключения контекста, если цикл оказывается достаточно длинным (примерно равным интервалу времени, необходимого для перехода в режим ядра). Например, на одноядерных компьютерах <xref:System.Threading.SpinWait> возвращает временной интервал потока немедленно, так как цикл блокирует дальнейшее выполнение всех потоков. <xref:System.Threading.SpinWait>также возвращает управление даже на многоядерных компьютерах для предотвращения блокировки потоков с более высоким приоритетом или сборщик мусора ожидающий поток. Таким образом Если вы используете <xref:System.Threading.SpinWait> в двухэтапной операции ожидания, рекомендуется вызвать ожидания ядра перед <xref:System.Threading.SpinWait> сам инициирует переключение контекста. <xref:System.Threading.SpinWait>предоставляет <xref:System.Threading.SpinWait.NextSpinWillYield%2A> свойство, которое можно проверять перед каждым вызовом <xref:System.Threading.SpinWait.SpinOnce%2A>. Если свойство возвращает `true`, Инициируйте собственную операцию ожидания. Пример см. в разделе [как: использование объекта SpinWait для реализации операции ожидания двухфазная](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Если вы не выполняете двухэтапной операции ожидания, но просто выполняется цикл до некоторого условия, можно включить <xref:System.Threading.SpinWait> для выполнения его контекст переключается так, чтобы он хорошо частные лица в среде операционной системы Windows. Следующем базовом примере показано <xref:System.Threading.SpinWait> стека, без блокировки. Если требуется высокой производительности, поточно ориентированного стека, рассмотрите возможность использования <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Thread.SpinWait%2A>  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
