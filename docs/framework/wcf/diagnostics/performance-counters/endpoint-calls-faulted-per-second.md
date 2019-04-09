---
title: 'Конечная точка: Количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: f425d95868a9ba5bc3c2f2291db2bc414b1918e2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122230"
---
# <a name="endpoint-calls-faulted-per-second"></a><span data-ttu-id="5bde3-102">Конечная точка: Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="5bde3-102">Endpoint: Calls Faulted Per Second</span></span>
<span data-ttu-id="5bde3-103">Имя счетчика: Количество сбоев вызовов в секунду.</span><span class="sxs-lookup"><span data-stu-id="5bde3-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5bde3-104">Описание</span><span class="sxs-lookup"><span data-stu-id="5bde3-104">Description</span></span>  
 <span data-ttu-id="5bde3-105">Количество вызовов, которые возвратили сбой данной конечной точке в секунду.</span><span class="sxs-lookup"><span data-stu-id="5bde3-105">Number of calls that have returned faults to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="5bde3-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="5bde3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5bde3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="5bde3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="5bde3-108">В приложениях Windows Communication Foundation (WCF) методы службы передают сведения об ошибке обработки с помощью сообщения об ошибках SOAP.</span><span class="sxs-lookup"><span data-stu-id="5bde3-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="5bde3-109">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="5bde3-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="5bde3-110">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="5bde3-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bde3-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5bde3-111">See also</span></span>

- [<span data-ttu-id="5bde3-112">Задание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="5bde3-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
