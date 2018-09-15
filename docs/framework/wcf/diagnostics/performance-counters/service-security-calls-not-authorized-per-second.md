---
title: 'Служба: количество неавторизованных вызовов системы безопасности в секунду'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: f2c921991f059d7dfe5661dfe688ec9675d0d5fe
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45625546"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="c4475-102">Служба: количество неавторизованных вызовов системы безопасности в секунду</span><span class="sxs-lookup"><span data-stu-id="c4475-102">Service: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="c4475-103">Имя счетчика: Security Calls Not Authorized Per Second</span><span class="sxs-lookup"><span data-stu-id="c4475-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="c4475-104">Описание</span><span class="sxs-lookup"><span data-stu-id="c4475-104">Description</span></span>  
 <span data-ttu-id="c4475-105">Число входящих сообщений в секунду, надлежаще защищенных и поступивших от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="c4475-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="c4475-106">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="c4475-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="c4475-107">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="c4475-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c4475-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="c4475-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
