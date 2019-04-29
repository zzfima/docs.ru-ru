---
title: 'Служба: Неавторизованные вызовы системы безопасности'
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
ms.openlocfilehash: a38b5e0eb467a5cad698fd6e3e01c0adef825d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773377"
---
# <a name="service-security-calls-not-authorized"></a><span data-ttu-id="bca97-102">Служба: Неавторизованные вызовы системы безопасности</span><span class="sxs-lookup"><span data-stu-id="bca97-102">Service: Security Calls Not Authorized</span></span>
<span data-ttu-id="bca97-103">Имя счетчика: Неавторизованные вызовы системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="bca97-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bca97-104">Описание</span><span class="sxs-lookup"><span data-stu-id="bca97-104">Description</span></span>  
 <span data-ttu-id="bca97-105">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="bca97-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="bca97-106">Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="bca97-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
