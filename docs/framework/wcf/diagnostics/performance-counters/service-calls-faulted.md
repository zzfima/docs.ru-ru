---
title: "Служба: сбои вызовов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f82558bdacbc36569329764aa1639c81146d9127
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="service-calls-faulted"></a><span data-ttu-id="9cb95-102">Служба: сбои вызовов</span><span class="sxs-lookup"><span data-stu-id="9cb95-102">Service: Calls Faulted</span></span>
<span data-ttu-id="9cb95-103">Имя счетчика: Calls Faulted</span><span class="sxs-lookup"><span data-stu-id="9cb95-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9cb95-104">Описание</span><span class="sxs-lookup"><span data-stu-id="9cb95-104">Description</span></span>  
 <span data-ttu-id="9cb95-105">Количество вызовов данной службы, которые возвратили сообщение о сбое.</span><span class="sxs-lookup"><span data-stu-id="9cb95-105">Number of calls to this service that have returned faults.</span></span> <span data-ttu-id="9cb95-106">В приложениях [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] методы служб передают информацию об ошибках обработки с помощью сообщений об ошибках SOAP.</span><span class="sxs-lookup"><span data-stu-id="9cb95-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="9cb95-107">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="9cb95-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="9cb95-108">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9cb95-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb95-109">См. также</span><span class="sxs-lookup"><span data-stu-id="9cb95-109">See Also</span></span>  
 [<span data-ttu-id="9cb95-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="9cb95-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
