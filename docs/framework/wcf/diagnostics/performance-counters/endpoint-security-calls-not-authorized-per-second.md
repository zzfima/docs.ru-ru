---
title: 'Конечная точка: Количество неавторизованных вызовов системы безопасности в секунду'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: c62bec570daf8b107ca0540871eb6eac43ca2d7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951118"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="7b07f-102">Конечная точка: Количество неавторизованных вызовов системы безопасности в секунду</span><span class="sxs-lookup"><span data-stu-id="7b07f-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="7b07f-103">Имя счетчика: Security Calls Not Authorized Per Second.</span><span class="sxs-lookup"><span data-stu-id="7b07f-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7b07f-104">Описание</span><span class="sxs-lookup"><span data-stu-id="7b07f-104">Description</span></span>  
 <span data-ttu-id="7b07f-105">Число входящих сообщений в секунду, которые защищены надлежащим образом и поступили от допустимого пользователя, но пользователю не разрешено выполнять определенные задачи.</span><span class="sxs-lookup"><span data-stu-id="7b07f-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="7b07f-106">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="7b07f-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="7b07f-107">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="7b07f-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7b07f-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="7b07f-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
