---
title: 'Конечная точка: Сбои вызовов'
ms.date: 03/30/2017
ms.assetid: 271e6284-9c4b-465f-b619-069e1555a5e4
ms.openlocfilehash: e46ca3034c69e46f0fef510f9035d2e1544fd72c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144980"
---
# <a name="endpoint-calls-faulted"></a><span data-ttu-id="b2499-102">Конечная точка: Сбои вызовов</span><span class="sxs-lookup"><span data-stu-id="b2499-102">Endpoint: Calls Faulted</span></span>
<span data-ttu-id="b2499-103">Имя счетчика: Количество сбоев вызовов.</span><span class="sxs-lookup"><span data-stu-id="b2499-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b2499-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b2499-104">Description</span></span>  
 <span data-ttu-id="b2499-105">Количество вызовов данной конечной точки, которые возвратили сбой.</span><span class="sxs-lookup"><span data-stu-id="b2499-105">Number of calls to this endpoint that have returned faults.</span></span> <span data-ttu-id="b2499-106">В приложениях Windows Communication Foundation (WCF) методы службы передают сведения об ошибке обработки с помощью сообщения об ошибках SOAP.</span><span class="sxs-lookup"><span data-stu-id="b2499-106">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="b2499-107">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="b2499-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="b2499-108">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="b2499-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2499-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b2499-109">See also</span></span>

- [<span data-ttu-id="b2499-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="b2499-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
