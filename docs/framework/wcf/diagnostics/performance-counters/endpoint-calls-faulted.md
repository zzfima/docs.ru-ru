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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33cedf5dc29e9cabc6fc3b7df8ff355605a112dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-calls-faulted"></a><span data-ttu-id="1547f-102">Конечная точка: сбои вызовов</span><span class="sxs-lookup"><span data-stu-id="1547f-102">Endpoint: Calls Faulted</span></span>
<span data-ttu-id="1547f-103">Имя счетчика: Calls Faulted</span><span class="sxs-lookup"><span data-stu-id="1547f-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1547f-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="1547f-104">Description</span></span>  
 <span data-ttu-id="1547f-105">Количество вызовов данной конечной точки, которые возвратили сбой.</span><span class="sxs-lookup"><span data-stu-id="1547f-105">Number of calls to this endpoint that have returned faults.</span></span> <span data-ttu-id="1547f-106">В приложениях [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] методы служб передают информацию об ошибках обработки с помощью сообщений об ошибках SOAP.</span><span class="sxs-lookup"><span data-stu-id="1547f-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="1547f-107">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="1547f-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="1547f-108">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="1547f-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1547f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1547f-109">See Also</span></span>  
 [<span data-ttu-id="1547f-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="1547f-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
