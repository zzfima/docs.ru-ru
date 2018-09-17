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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bc0c6bebbab6e84c165f41300a4cb16c8746a07
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45597307"
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="90096-102">Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="90096-102">How to: Create an Object Pool by Using a ConcurrentBag</span></span>
<span data-ttu-id="90096-103">В этом примере показано, как использовать контейнер ConcurrentBag для реализации пула объектов.</span><span class="sxs-lookup"><span data-stu-id="90096-103">This example shows how to use a concurrent bag to implement an object pool.</span></span> <span data-ttu-id="90096-104">Пулы объектов позволяют улучшить производительность приложения, когда требуется несколько экземпляров класса, которые "дорого" создавать или уничтожать.</span><span class="sxs-lookup"><span data-stu-id="90096-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="90096-105">Когда клиентская программа запрашивает новый объект, сперва происходит поиск в пуле объектов ранее созданного и возвращенного в пул объекта.</span><span class="sxs-lookup"><span data-stu-id="90096-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="90096-106">Новый объект создается, только если в пуле не нашлось нужного объекта.</span><span class="sxs-lookup"><span data-stu-id="90096-106">If none is available, only then is a new object created.</span></span>  
  
 <span data-ttu-id="90096-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> используется для хранения объектов, так как поддерживает быстрое добавление и удаление, особенно при добавлении и удалении элементов одним потоком.</span><span class="sxs-lookup"><span data-stu-id="90096-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="90096-108">Этот пример можно расширить до построения на основе интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, который реализует структура данных контейнера, например <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="90096-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90096-109">Пример</span><span class="sxs-lookup"><span data-stu-id="90096-109">Example</span></span>  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="90096-110">См. также</span><span class="sxs-lookup"><span data-stu-id="90096-110">See also</span></span>

- [<span data-ttu-id="90096-111">Потокобезопасные коллекции</span><span class="sxs-lookup"><span data-stu-id="90096-111">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
