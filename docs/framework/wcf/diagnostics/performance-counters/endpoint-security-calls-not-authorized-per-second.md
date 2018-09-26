---
title: 'Конечная точка: количество неавторизованных вызовов системы безопасности в секунду'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
author: BrucePerlerMS
ms.openlocfilehash: 4abea795eb196d339beec17fa7a171927aa85324
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078374"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="19108-102">Конечная точка: количество неавторизованных вызовов системы безопасности в секунду</span><span class="sxs-lookup"><span data-stu-id="19108-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="19108-103">Имя счетчика: Security Calls Not Authorized Per Second.</span><span class="sxs-lookup"><span data-stu-id="19108-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="19108-104">Описание</span><span class="sxs-lookup"><span data-stu-id="19108-104">Description</span></span>  
 <span data-ttu-id="19108-105">Число входящих сообщений в секунду, которые защищены надлежащим образом и поступили от допустимого пользователя, но пользователю не разрешено выполнять определенные задачи.</span><span class="sxs-lookup"><span data-stu-id="19108-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="19108-106">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="19108-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="19108-107">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="19108-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="19108-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="19108-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
