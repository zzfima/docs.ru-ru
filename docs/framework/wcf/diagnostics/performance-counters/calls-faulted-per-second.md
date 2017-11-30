---
title: "Количество сбоев вызовов в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e60ad3d7e9155eecfead38aca080a3044b0efce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="b3f5e-102">Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="b3f5e-102">Calls Faulted Per Second</span></span>
<span data-ttu-id="b3f5e-103">Имя счетчика: Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="b3f5e-103">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="b3f5e-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b3f5e-104">Description</span></span>  
 <span data-ttu-id="b3f5e-105">Число вызовов, возвращающих ошибки этой операции за секунду.</span><span class="sxs-lookup"><span data-stu-id="b3f5e-105">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="b3f5e-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="b3f5e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b3f5e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b3f5e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="b3f5e-108">В приложениях [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] методы служб передают информацию об ошибках обработки с помощью сообщений об ошибках SOAP.</span><span class="sxs-lookup"><span data-stu-id="b3f5e-108">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="b3f5e-109">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="b3f5e-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="b3f5e-110">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="b3f5e-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f5e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b3f5e-111">See Also</span></span>  
 [<span data-ttu-id="b3f5e-112">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="b3f5e-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
