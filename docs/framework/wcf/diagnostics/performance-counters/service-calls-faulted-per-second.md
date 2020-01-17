---
title: 'Служба: количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: ba470c565c042de6de53693e7b0e6d4682c5a75a
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163896"
---
# <a name="service-calls-faulted-per-second"></a><span data-ttu-id="33eec-102">Служба: количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="33eec-102">Service: Calls Faulted Per Second</span></span>
<span data-ttu-id="33eec-103">Имя счетчика: Calls Faulted Per Second.</span><span class="sxs-lookup"><span data-stu-id="33eec-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="33eec-104">Описание</span><span class="sxs-lookup"><span data-stu-id="33eec-104">Description</span></span>  
 <span data-ttu-id="33eec-105">Число вызовов, которые возвратили сбой этой службе за секунду.</span><span class="sxs-lookup"><span data-stu-id="33eec-105">Number of calls that have returned faults to this service in a second.</span></span>  
  
 <span data-ttu-id="33eec-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="33eec-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="33eec-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="33eec-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="33eec-108">В приложениях Windows Communication Foundation (WCF) методы служб обмениваются сведениями об ошибках обработки с помощью сообщений о сбоях SOAP.</span><span class="sxs-lookup"><span data-stu-id="33eec-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="33eec-109">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="33eec-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="33eec-110">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="33eec-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33eec-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="33eec-111">See also</span></span>

- [<span data-ttu-id="33eec-112">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="33eec-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
