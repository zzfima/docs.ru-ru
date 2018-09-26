---
title: 'Служба: количество неавторизованных вызовов системы безопасности в секунду'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
author: BrucePerlerMS
ms.openlocfilehash: 17da19e88dfa837cc1e45d0b6af2ebdbfd00182c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157134"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="60a55-102">Служба: количество неавторизованных вызовов системы безопасности в секунду</span><span class="sxs-lookup"><span data-stu-id="60a55-102">Service: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="60a55-103">Имя счетчика: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="60a55-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="60a55-104">Описание</span><span class="sxs-lookup"><span data-stu-id="60a55-104">Description</span></span>  
 <span data-ttu-id="60a55-105">Число входящих сообщений в секунду, надлежаще защищенных и поступивших от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="60a55-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="60a55-106">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="60a55-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="60a55-107">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="60a55-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="60a55-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="60a55-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
