---
title: Сбои вызовов
ms.date: 03/30/2017
ms.assetid: bb9e8045-6aeb-4b7f-a825-8283c44252a1
ms.openlocfilehash: 63181078da4ce75b5b5f68a2d40ad5338a687968
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095261"
---
# <a name="calls-faulted"></a><span data-ttu-id="0f332-102">Сбои вызовов</span><span class="sxs-lookup"><span data-stu-id="0f332-102">Calls Faulted</span></span>
<span data-ttu-id="0f332-103">Имя счетчика: Сбои вызовов</span><span class="sxs-lookup"><span data-stu-id="0f332-103">Counter Name: Calls Faulted</span></span>  
  
## <a name="description"></a><span data-ttu-id="0f332-104">Описание</span><span class="sxs-lookup"><span data-stu-id="0f332-104">Description</span></span>  
 <span data-ttu-id="0f332-105">Количество неудачных вызовов данной операции.</span><span class="sxs-lookup"><span data-stu-id="0f332-105">Number of calls to this operation that returned faults.</span></span> <span data-ttu-id="0f332-106">В приложениях Windows Communication Foundation (WCF) методы службы передают сведения об ошибке обработки с помощью сообщения об ошибках SOAP.</span><span class="sxs-lookup"><span data-stu-id="0f332-106">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="0f332-107">Сообщения об ошибках SOAP - это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.</span><span class="sxs-lookup"><span data-stu-id="0f332-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="0f332-108">Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="0f332-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f332-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0f332-109">See also</span></span>

- [<span data-ttu-id="0f332-110">Задание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="0f332-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
