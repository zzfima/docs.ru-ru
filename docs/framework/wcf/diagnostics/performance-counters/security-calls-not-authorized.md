---
title: Неавторизованные вызовы системы безопасности
ms.date: 03/30/2017
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 3554644a7f73894703cc26ad11e4f7b9d58cab60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472577"
---
# <a name="security-calls-not-authorized"></a><span data-ttu-id="c6c71-102">Неавторизованные вызовы системы безопасности</span><span class="sxs-lookup"><span data-stu-id="c6c71-102">Security Calls Not Authorized</span></span>
<span data-ttu-id="c6c71-103">Имя счетчика: Security Calls Not Authorized.</span><span class="sxs-lookup"><span data-stu-id="c6c71-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c6c71-104">Описание</span><span class="sxs-lookup"><span data-stu-id="c6c71-104">Description</span></span>  
 <span data-ttu-id="c6c71-105">Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="c6c71-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="c6c71-106">Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.</span><span class="sxs-lookup"><span data-stu-id="c6c71-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
