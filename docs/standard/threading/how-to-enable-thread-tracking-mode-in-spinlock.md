---
title: Практическое руководство. Включение режима отслеживания потоков в SpinLock
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
ms.openlocfilehash: f52a844284cf46bcace3f54f8b320d336050a64e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138035"
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>Практическое руководство. Включение режима отслеживания потоков в SpinLock
<xref:System.Threading.SpinLock?displayProperty=nameWithType> реализует низкоуровневую взаимоисключающую блокировку, которая применима для сценариев с очень коротким временем ожидания. <xref:System.Threading.SpinLock> не допускает повторный вход. После входа потока в блокировку он обязан правильно завершить блокировку, прежде чем входить в нее повторно. Как правило, любая попытка повторно войти в блокировку приводит к взаимоблокировке, что иногда очень трудно подвергается отладке. Для помощи разработчикам <xref:System.Threading.SpinLock?displayProperty=nameWithType> поддерживает режим отслеживания потоков, в котором создается исключение, когда поток пытается повторно войти в уже открытую блокировку. Это позволяет быстрее найти точку, в которой неправильно выполнен выход из блокировки. Чтобы включить режим отслеживания потоков, используйте конструктор <xref:System.Threading.SpinLock>, который принимает на вход логический параметр, в котором следует передать значение `true`. Завершив все этапы разработки и тестирования, обязательно отключите режим отслеживания потоков, чтобы он не влиял на производительность.  
  
## <a name="example"></a>Пример  
 В примере ниже демонстрируется режим отслеживания потоков. Здесь закомментированы строки, в которых блокировка завершена правильно, чтобы смоделировать ошибку, приводящую к одному из следующих результатов:  
  
- Создается исключение, если <xref:System.Threading.SpinLock> создан с аргументом `true` (`True` в Visual Basic).  
  
- Возникает взаимоблокировка, если <xref:System.Threading.SpinLock> создан с аргументом `false` (`False` в Visual Basic).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>См. также

- [SpinLock](../../../docs/standard/threading/spinlock.md)
