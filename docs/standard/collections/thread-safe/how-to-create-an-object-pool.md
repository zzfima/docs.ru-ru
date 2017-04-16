---
title: "Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag | Microsoft Docs"
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
  - "пул объектов, в .NET Framework"
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag
В этом примере показано, как использовать контейнер ConcurrentBag для реализации пула объектов.  Пулы объектов позволяют улучшить производительность приложения, когда требуется несколько экземпляров класса, которые "дорого" создавать или уничтожать.  Когда клиентская программа запрашивает новый объект, сперва происходит поиск в пуле объектов ранее созданного и возвращенного в пул объекта.  Новый объект создается, только если в пуле не нашлось нужного объекта.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601> используется для хранения объектов, поскольку поддерживает быстрое добавление и удаление, особенно при добавлении и удалении элементов одним потоком.  Этот пример можно расширить до построения вокруг интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, который реализует структура данных контейнера, например <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
## Пример  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## См. также  
 [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)