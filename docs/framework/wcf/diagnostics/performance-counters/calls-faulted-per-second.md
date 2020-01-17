---
title: Количество сбоев вызовов в секунду
ms.date: 03/30/2017
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
ms.openlocfilehash: 37fd47a3e4ca474338a4a6ae1117c2626acb546f
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163154"
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="6d227-102">Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="6d227-102">Calls Faulted Per Second</span></span>
<span data-ttu-id="6d227-103">Имя счетчика: Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="6d227-103">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="6d227-104">Описание</span><span class="sxs-lookup"><span data-stu-id="6d227-104">Description</span></span>  
 <span data-ttu-id="6d227-105">Число вызовов, возвращающих ошибки этой операции за секунду.</span><span class="sxs-lookup"><span data-stu-id="6d227-105">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="6d227-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="6d227-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6d227-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6d227-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="6d227-108">В приложениях Windows Communication Foundation (WCF) методы служб обмениваются сведениями об ошибках обработки с помощью сообщений о сбоях SOAP.</span><span class="sxs-lookup"><span data-stu-id="6d227-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="6d227-109">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="6d227-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="6d227-110">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6d227-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d227-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="6d227-111">See also</span></span>

- [<span data-ttu-id="6d227-112">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="6d227-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
