---
title: "Практическое руководство. Добавление функций границы и блокировки в коллекцию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3258534cb0bf67b180080eca4f7cefc65c609fa4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a>Практическое руководство. Добавление функций границы и блокировки в коллекцию
В этом примере показано, как добавлять функциональные возможности границ и блокировок в пользовательский класс коллекции путем реализации интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> в классе и последующего использования экземпляра класса в качестве механизма внутреннего хранения для объекта класса <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>. Дополнительные сведения о границах и блокировках см. в разделе [Общие сведения о коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
## <a name="example"></a>Пример  
 Пользовательский класс коллекции является базовой очередью с приоритетами, в которой уровни приоритета представляются в виде массива объектов класса <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>. Внутри каждой очереди дополнительное упорядочивание не выполняется.  
  
 В клиентском коде запускаются три задачи. Первая задача просто запрашивает нажатие клавиш, чтобы включить отмену в любой момент во время выполнения. Вторая задача является потоком-производителем. Он добавляет новые элементы в заблокированную коллекцию и дает каждому элементу приоритет на основе случайного значения. Третья задача выполняет удаление элементов из коллекции, как только они становятся доступными.  
  
 Настройку поведения приложения можно выполнять с помощью задания более быстрого выполнения одного из потоков по сравнению с другими. Если производитель выполняется быстрее, можно увидеть ограничение функциональных возможностей, так как заблокированная коллекция предупреждает добавление элементов, если она уже содержит количество элементов, которое задано в конструкторе. Если объект-получатель выполняется быстрее, можно увидеть ограничение функциональных возможностей, так как объект-получатель ожидает добавления нового элемента.  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 По умолчанию хранилищем для <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> является <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)

