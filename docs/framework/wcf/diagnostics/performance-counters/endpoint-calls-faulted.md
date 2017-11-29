---
title: "Конечная точка: сбои вызовов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 271e6284-9c4b-465f-b619-069e1555a5e4
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d62eb1ad10c7112696d8fa2a358db4c88ee86cb3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-faulted"></a><span data-ttu-id="b5171-102">Конечная точка: сбои вызовов</span><span class="sxs-lookup"><span data-stu-id="b5171-102">Endpoint: Calls Faulted</span></span>
<span data-ttu-id="b5171-103">Имя счетчика: Calls Faulted</span><span class="sxs-lookup"><span data-stu-id="b5171-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b5171-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b5171-104">Description</span></span>  
 <span data-ttu-id="b5171-105">Количество вызовов данной конечной точки, которые возвратили сбой.</span><span class="sxs-lookup"><span data-stu-id="b5171-105">Number of calls to this endpoint that have returned faults.</span></span> <span data-ttu-id="b5171-106">В приложениях [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] методы служб передают информацию об ошибках обработки с помощью сообщений об ошибках SOAP.</span><span class="sxs-lookup"><span data-stu-id="b5171-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="b5171-107">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="b5171-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="b5171-108">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="b5171-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5171-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b5171-109">See Also</span></span>  
 [<span data-ttu-id="b5171-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="b5171-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
