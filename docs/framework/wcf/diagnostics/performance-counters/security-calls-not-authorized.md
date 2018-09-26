---
title: Неавторизованные вызовы системы безопасности
ms.date: 03/30/2017
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
author: BrucePerlerMS
ms.openlocfilehash: 6af1c7576e6a0fe7ae21f6f1997b2ebe3b919214
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111910"
---
# <a name="security-calls-not-authorized"></a><span data-ttu-id="8339b-102">Неавторизованные вызовы системы безопасности</span><span class="sxs-lookup"><span data-stu-id="8339b-102">Security Calls Not Authorized</span></span>
<span data-ttu-id="8339b-103">Имя счетчика: Security Calls Not Authorized.</span><span class="sxs-lookup"><span data-stu-id="8339b-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8339b-104">Описание</span><span class="sxs-lookup"><span data-stu-id="8339b-104">Description</span></span>  
 <span data-ttu-id="8339b-105">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8339b-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="8339b-106">Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="8339b-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
