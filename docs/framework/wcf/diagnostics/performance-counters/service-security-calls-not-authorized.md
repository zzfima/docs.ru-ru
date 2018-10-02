---
title: 'Служба: количество неавторизованных вызовов системы безопасности'
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
author: BrucePerlerMS
ms.openlocfilehash: f90ed5746c8b798e55b7e300ba7ff63bbafdcac4
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035887"
---
# <a name="service-security-calls-not-authorized"></a><span data-ttu-id="d30d9-102">Служба: количество неавторизованных вызовов системы безопасности</span><span class="sxs-lookup"><span data-stu-id="d30d9-102">Service: Security Calls Not Authorized</span></span>
<span data-ttu-id="d30d9-103">Имя счетчика: Security Calls Not Authorized.</span><span class="sxs-lookup"><span data-stu-id="d30d9-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d30d9-104">Описание</span><span class="sxs-lookup"><span data-stu-id="d30d9-104">Description</span></span>  
 <span data-ttu-id="d30d9-105">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d30d9-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="d30d9-106">Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="d30d9-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
