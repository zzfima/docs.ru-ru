---
title: 'Конечная точка: количество неавторизованных вызовов системы безопасности в секунду'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: 8c287ef4c156bb0a76a4b1d08b0d70b40bd76229
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163180"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="b9aa0-102">Конечная точка: количество неавторизованных вызовов системы безопасности в секунду</span><span class="sxs-lookup"><span data-stu-id="b9aa0-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="b9aa0-103">Имя счетчика: Security Calls Not Authorized Per Second.</span><span class="sxs-lookup"><span data-stu-id="b9aa0-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b9aa0-104">Описание</span><span class="sxs-lookup"><span data-stu-id="b9aa0-104">Description</span></span>  
 <span data-ttu-id="b9aa0-105">Число входящих сообщений в секунду, которые защищены надлежащим образом и поступили от допустимого пользователя, но пользователю не разрешено выполнять определенные задачи.</span><span class="sxs-lookup"><span data-stu-id="b9aa0-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="b9aa0-106">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b9aa0-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="b9aa0-107">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="b9aa0-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b9aa0-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b9aa0-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
