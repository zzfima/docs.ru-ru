---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a>SpinLock
<xref:System.Threading.SpinLock> Структуры — это низкоуровневые взаимного исключения примитив синхронизации, который выполняет цикл в ожидании получения блокировки. На многоядерных компьютерах, если предполагается, что время ожидания короткий и будет минимально и <xref:System.Threading.SpinLock> можно выполнить быстрее, чем другие виды блокировок. Тем не менее, мы рекомендуем использовать <xref:System.Threading.SpinLock> только при определении профилирования показывают, что <xref:System.Threading.Monitor?displayProperty=nameWithType> метода или <xref:System.Threading.Interlocked> методы значительно снижают производительность программы.  
  
 <xref:System.Threading.SpinLock>может привести временной срез потока, даже если он ещё не получила блокировку. Это делается во избежание инверсии приоритет потока, а также поддерживать сборщик мусора прогресса. При использовании <xref:System.Threading.SpinLock>, убедитесь, что ни один поток не может быть установлена блокировка более короткая временной интервал, и что ни один поток можно заблокировать во время удержания блокировки.  
  
 Поскольку SpinLock является типом значения, необходимо явным образом передать его по ссылке, если планируется две копии для ссылки на ту же блокировку.  
  
 Дополнительные сведения об использовании этого типа см. в разделе <xref:System.Threading.SpinLock?displayProperty=nameWithType>. Пример см. в разделе [как: SpinLock используется для синхронизации нижнего уровня](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock>поддерживает *поток*-*отслеживания* режим, который можно использовать на этапе разработки для отслеживания потока, который удерживает блокировку в определенное время. Режим отслеживания потоков очень полезен для отладки, но мы рекомендуем отключить его в окончательной версии программы, так как может привести к снижению производительности. Дополнительные сведения см. в разделе [как: режим включить поток отслеживания в SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## <a name="see-also"></a>См. также  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)
