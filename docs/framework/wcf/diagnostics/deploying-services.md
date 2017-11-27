---
title: "Развертывание служб"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75069b00fa07078ff0eb2d49e64f046d5415d154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-services"></a><span data-ttu-id="4da39-102">Развертывание служб</span><span class="sxs-lookup"><span data-stu-id="4da39-102">Deploying Services</span></span>
<span data-ttu-id="4da39-103">В этом разделе описывается развертывание приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="4da39-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="4da39-104">Выбор среды размещения для приложения</span><span class="sxs-lookup"><span data-stu-id="4da39-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="4da39-105">Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предназначены для выполнения в любом процессе Windows, который поддерживает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="4da39-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="4da39-106">Для активации службы ее необходимо разместить в среде выполнения, которая создает эту службу и управляет ее контекстом и временем существования.</span><span class="sxs-lookup"><span data-stu-id="4da39-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="4da39-107">Варианты размещения могут быть самыми различными - от выполнения внутри простейшего консольного приложения до работы в серверных средах (таких как службы Windows, службы IIS) или внутри рабочего процесса, управляемого службой активации Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="4da39-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="4da39-108">Для просмотра различных вариантов размещения для вашего [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приложения, в разделе [размещение служб](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="4da39-108">To review the different hosting options for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da39-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4da39-109">See Also</span></span>  
 [<span data-ttu-id="4da39-110">Размещение</span><span class="sxs-lookup"><span data-stu-id="4da39-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="4da39-111">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="4da39-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
