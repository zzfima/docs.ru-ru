---
title: "Сбои вызовов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb9e8045-6aeb-4b7f-a825-8283c44252a1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8eba92f70c2534d854c1e7f747d610ca30700aac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="calls-faulted"></a><span data-ttu-id="0e0d9-102">Сбои вызовов</span><span class="sxs-lookup"><span data-stu-id="0e0d9-102">Calls Faulted</span></span>
<span data-ttu-id="0e0d9-103">Имя счетчика: Calls Faulted</span><span class="sxs-lookup"><span data-stu-id="0e0d9-103">Counter Name: Calls Faulted</span></span>  
  
## <a name="description"></a><span data-ttu-id="0e0d9-104">Описание</span><span class="sxs-lookup"><span data-stu-id="0e0d9-104">Description</span></span>  
 <span data-ttu-id="0e0d9-105">Количество неудачных вызовов данной операции.</span><span class="sxs-lookup"><span data-stu-id="0e0d9-105">Number of calls to this operation that returned faults.</span></span> <span data-ttu-id="0e0d9-106">В приложениях [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] методы служб передают информацию об ошибках обработки с помощью сообщений об ошибках SOAP.</span><span class="sxs-lookup"><span data-stu-id="0e0d9-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="0e0d9-107">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="0e0d9-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="0e0d9-108">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="0e0d9-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0d9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0e0d9-109">See Also</span></span>  
 [<span data-ttu-id="0e0d9-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="0e0d9-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
