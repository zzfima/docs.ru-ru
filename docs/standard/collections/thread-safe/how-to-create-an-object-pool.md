---
title: "Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag"
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
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 66cde52d7453e149510d0c2e1d63f9e9182e3e99
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="5a338-102">Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="5a338-102">How to: Create an Object Pool by Using a ConcurrentBag</span></span>
<span data-ttu-id="5a338-103">В этом примере показано, как использовать контейнер ConcurrentBag для реализации пула объектов.</span><span class="sxs-lookup"><span data-stu-id="5a338-103">This example shows how to use a concurrent bag to implement an object pool.</span></span> <span data-ttu-id="5a338-104">Пулы объектов позволяют улучшить производительность приложения, когда требуется несколько экземпляров класса, которые "дорого" создавать или уничтожать.</span><span class="sxs-lookup"><span data-stu-id="5a338-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="5a338-105">Когда клиентская программа запрашивает новый объект, сперва происходит поиск в пуле объектов ранее созданного и возвращенного в пул объекта.</span><span class="sxs-lookup"><span data-stu-id="5a338-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="5a338-106">Новый объект создается, только если в пуле не нашлось нужного объекта.</span><span class="sxs-lookup"><span data-stu-id="5a338-106">If none is available, only then is a new object created.</span></span>  
  
 <span data-ttu-id="5a338-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> используется для хранения объектов, так как поддерживает быстрое добавление и удаление, особенно при добавлении и удалении элементов одним потоком.</span><span class="sxs-lookup"><span data-stu-id="5a338-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="5a338-108">Этот пример можно расширить до построения на основе интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, который реализует структура данных контейнера, например <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="5a338-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a338-109">Пример</span><span class="sxs-lookup"><span data-stu-id="5a338-109">Example</span></span>  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="5a338-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5a338-110">See Also</span></span>  
 [<span data-ttu-id="5a338-111">Потокобезопасные коллекции</span><span class="sxs-lookup"><span data-stu-id="5a338-111">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
