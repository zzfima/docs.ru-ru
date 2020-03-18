---
title: Практическое руководство. Добавление функций границы и блокировки в коллекцию
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
ms.openlocfilehash: 33c0b5a93a9c63e3e743a04e69bb7353ac69fa8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711289"
---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a>Практическое руководство. Добавление функций границы и блокировки в коллекцию
В этом примере показано, как добавлять функциональные возможности границ и блокировок в пользовательский класс коллекции путем реализации интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> в классе и последующего использования экземпляра класса в качестве механизма внутреннего хранения для объекта класса <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>. Дополнительные сведения о границах и блокировках см. в разделе [Общие сведения о коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
## <a name="example"></a>Пример  
 Пользовательский класс коллекции является базовой очередью с приоритетами, в которой уровни приоритета представляются в виде массива объектов класса <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>. Внутри каждой очереди дополнительное упорядочивание не выполняется.  
  
 В клиентском коде запускаются три задачи. Первая задача просто запрашивает нажатие клавиш, чтобы включить отмену в любой момент во время выполнения. Вторая задача является потоком-производителем. Он добавляет новые элементы в заблокированную коллекцию и дает каждому элементу приоритет на основе случайного значения. Третья задача выполняет удаление элементов из коллекции, как только они становятся доступными.  
  
 Настройку поведения приложения можно выполнять с помощью задания более быстрого выполнения одного из потоков по сравнению с другими. Если производитель выполняется быстрее, можно увидеть ограничение функциональных возможностей, так как заблокированная коллекция предупреждает добавление элементов, если она уже содержит количество элементов, которое задано в конструкторе. Если объект-получатель выполняется быстрее, можно увидеть ограничение функциональных возможностей, так как объект-получатель ожидает добавления нового элемента.  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 По умолчанию хранилищем для <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> является <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)
