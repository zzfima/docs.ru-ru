---
title: "Служба: количество неавторизованных вызовов системы безопасности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 5dae370d90082c9efe89f9d523740fc25ece21ab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-calls-not-authorized"></a><span data-ttu-id="d7cdb-102">Служба: количество неавторизованных вызовов системы безопасности</span><span class="sxs-lookup"><span data-stu-id="d7cdb-102">Service: Security Calls Not Authorized</span></span>
<span data-ttu-id="d7cdb-103">Имя счетчика: Security Calls Not Authorized.</span><span class="sxs-lookup"><span data-stu-id="d7cdb-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d7cdb-104">Описание</span><span class="sxs-lookup"><span data-stu-id="d7cdb-104">Description</span></span>  
 <span data-ttu-id="d7cdb-105">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d7cdb-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="d7cdb-106">Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="d7cdb-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
