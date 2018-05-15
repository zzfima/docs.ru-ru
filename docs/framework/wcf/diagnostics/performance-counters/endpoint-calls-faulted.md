---
title: 'Конечная точка: сбои вызовов'
ms.date: 03/30/2017
ms.assetid: 271e6284-9c4b-465f-b619-069e1555a5e4
ms.openlocfilehash: 126ba1b4bd2cc16d62460f198a69194fe4652a4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="endpoint-calls-faulted"></a><span data-ttu-id="6e156-102">Конечная точка: сбои вызовов</span><span class="sxs-lookup"><span data-stu-id="6e156-102">Endpoint: Calls Faulted</span></span>
<span data-ttu-id="6e156-103">Имя счетчика: Calls Faulted</span><span class="sxs-lookup"><span data-stu-id="6e156-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6e156-104">Описание</span><span class="sxs-lookup"><span data-stu-id="6e156-104">Description</span></span>  
 <span data-ttu-id="6e156-105">Количество вызовов данной конечной точки, которые возвратили сбой.</span><span class="sxs-lookup"><span data-stu-id="6e156-105">Number of calls to this endpoint that have returned faults.</span></span> <span data-ttu-id="6e156-106">В приложениях Windows Communication Foundation (WCF), методы службы передают сведения об ошибке обработки с помощью сообщений об ошибках SOAP.</span><span class="sxs-lookup"><span data-stu-id="6e156-106">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="6e156-107">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="6e156-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="6e156-108">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6e156-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e156-109">См. также</span><span class="sxs-lookup"><span data-stu-id="6e156-109">See Also</span></span>  
 [<span data-ttu-id="6e156-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="6e156-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
