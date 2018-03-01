---
title: "Использование потоков и работа с потоками"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5bed13950a29cfa787ef8c9eb2608c6d74dfd49f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="using-threads-and-threading"></a>Использование потоков и работа с потоками
В статьях этого раздела мы обсуждаем создание управляемых потоков и управление ими, передачу данных в управляемые потоки и получение из них результатов, а также уничтожение потоков и обработку <xref:System.Threading.ThreadAbortException>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание потоков и передача данных во время запуска](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 Обсуждается и демонстрируется создание управляемых потоков, в том числе способы передать данные в новые потоки и получить данные из них.  
  
 [Приостановка и возобновление потоков](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 Обсуждаются сложности при приостановке и возобновлении управляемых потоков.  
  
 [Удаление потоков](../../../docs/standard/threading/destroying-threads.md)  
 Обсуждаются сложности при уничтожении управляемых потоков и обработка <xref:System.Threading.ThreadAbortException>.  
  
 [Планирование потоков](../../../docs/standard/threading/scheduling-threads.md)  
 Обсуждаются приоритеты потоков и их влияние на выполнение потоков.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Threading.Thread>  
 Справочная документация по классу <xref:System.Threading.Thread>, который представляет управляемый поток, созданный из неуправляемого кода или в управляемом приложении.  
  
 <xref:System.Threading.ThreadStart>  
 Справочная документация по делегату <xref:System.Threading.ThreadStart>, который представляет процедуры потоков без параметров.  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 Предоставляет простой способ передать данные в процедуру потока, но не поддерживает строгую типизацию.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Потоки и работа с потоками](../../../docs/standard/threading/threads-and-threading.md)  
 Общие сведения о работе с управляемыми потоками.
