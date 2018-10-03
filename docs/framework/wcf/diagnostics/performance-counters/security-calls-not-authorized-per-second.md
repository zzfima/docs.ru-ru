---
title: Количество неавторизованных вызовов системы безопасности в секунду
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
author: BrucePerlerMS
ms.openlocfilehash: 20c8da5fcdca0c99fd53fb5ce0d7cbf15552997a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035757"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="e70ed-102">Количество неавторизованных вызовов системы безопасности в секунду</span><span class="sxs-lookup"><span data-stu-id="e70ed-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="e70ed-103">Имя счетчика: Security Calls Not Authorized Per Second.</span><span class="sxs-lookup"><span data-stu-id="e70ed-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e70ed-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e70ed-104">Description</span></span>  
 <span data-ttu-id="e70ed-105">Число вызовов, которые не удалось авторизовать в данной операции, в секунду.</span><span class="sxs-lookup"><span data-stu-id="e70ed-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="e70ed-106">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e70ed-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="e70ed-107">Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="e70ed-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="e70ed-108">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="e70ed-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e70ed-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e70ed-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
