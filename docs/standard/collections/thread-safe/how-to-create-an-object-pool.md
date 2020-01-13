---
title: Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: 888521eb5c3c3169c4b39a26e82fef2e35c286d9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711276"
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a>Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag
В этом примере показано, как использовать контейнер ConcurrentBag для реализации пула объектов. Пулы объектов позволяют улучшить производительность приложения, когда требуется несколько экземпляров класса, которые "дорого" создавать или уничтожать. Когда клиентская программа запрашивает новый объект, сперва происходит поиск в пуле объектов ранее созданного и возвращенного в пул объекта. Новый объект создается, только если в пуле не нашлось нужного объекта.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601> используется для хранения объектов, так как поддерживает быстрое добавление и удаление, особенно при добавлении и удалении элементов одним потоком. Этот пример можно расширить до построения на основе интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, который реализует структура данных контейнера, например <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
## <a name="example"></a>Пример  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a>См. также

- [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)
