---
title: "Практическое руководство. Включение режима отслеживания потоков в SpinLock"
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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>Практическое руководство. Включение режима отслеживания потоков в SpinLock
<xref:System.Threading.SpinLock?displayProperty=nameWithType>Это низкоуровневая взаимно исключающая блокировка, который можно использовать для сценариев с очень короткими временами ожидания. <xref:System.Threading.SpinLock>не является реентерабельным. После поток вошел в блокировку, его необходимо закрыть блокировки правильно, прежде чем он сможет войти повторно. Как правило любая попытка повторно войти в блокировку может привести к взаимоблокировке и взаимоблокировки может быть очень трудно отлаживать. Как вспомогательное средство для разработки <xref:System.Threading.SpinLock?displayProperty=nameWithType> поддерживает режим отслеживания потоков, который вызывает исключение, если поток пытается повторно войти, уже удерживает блокировку. Это позволяет более легко обнаружить точку с которой блокировка была не завершен правильно. Режим отслеживания потоков можно включить с помощью <xref:System.Threading.SpinLock> конструктора, принимающего логический входной параметр и передачи аргумента `true`. После завершения разработки и тестирования, отключите режим отслеживания потоков для повышения производительности.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример режима отслеживания потоков. Строки, которые правильно выходит из нее, закомментированы, чтобы сымитировать ошибку кода, приводящую к одному из следующих результатов:  
  
-   Исключение возникает, если <xref:System.Threading.SpinLock> была создана с помощью аргумента `true` (`True` в Visual Basic).  
  
-   Взаимоблокировки <xref:System.Threading.SpinLock> была создана с помощью аргумента `false` (`False` в Visual Basic).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>См. также  
 [SpinLock](../../../docs/standard/threading/spinlock.md)
