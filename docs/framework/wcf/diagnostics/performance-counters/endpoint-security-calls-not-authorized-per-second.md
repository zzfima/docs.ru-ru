---
title: 'Конечная точка: количество неавторизованных вызовов системы безопасности в секунду'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: c62bec570daf8b107ca0540871eb6eac43ca2d7e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188356"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="dc60e-102">Конечная точка: количество неавторизованных вызовов системы безопасности в секунду</span><span class="sxs-lookup"><span data-stu-id="dc60e-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="dc60e-103">Имя счетчика: Security Calls Not Authorized Per Second.</span><span class="sxs-lookup"><span data-stu-id="dc60e-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="dc60e-104">Описание</span><span class="sxs-lookup"><span data-stu-id="dc60e-104">Description</span></span>  
 <span data-ttu-id="dc60e-105">Число входящих сообщений в секунду, которые защищены надлежащим образом и поступили от допустимого пользователя, но пользователю не разрешено выполнять определенные задачи.</span><span class="sxs-lookup"><span data-stu-id="dc60e-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="dc60e-106">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="dc60e-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="dc60e-107">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="dc60e-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="dc60e-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="dc60e-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
