---
title: Развертывание служб
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 4d9efcb4da064021d93345285982c0cbd29dde2e
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="deploying-services"></a><span data-ttu-id="e6af9-102">Развертывание служб</span><span class="sxs-lookup"><span data-stu-id="e6af9-102">Deploying Services</span></span>
<span data-ttu-id="e6af9-103">В этом разделе описывается развертывание приложения в среде выполнения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e6af9-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="e6af9-104">Выбор среды размещения для приложения</span><span class="sxs-lookup"><span data-stu-id="e6af9-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="e6af9-105">Службы WCF, предназначены для выполнения в любом процессе Windows, который поддерживает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="e6af9-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="e6af9-106">Для активации службы ее необходимо разместить в среде выполнения, которая создает эту службу и управляет ее контекстом и временем существования.</span><span class="sxs-lookup"><span data-stu-id="e6af9-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="e6af9-107">Варианты размещения могут быть самыми различными - от выполнения внутри простейшего консольного приложения до работы в серверных средах (таких как службы Windows, службы IIS) или внутри рабочего процесса, управляемого службой активации Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="e6af9-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="e6af9-108">Для просмотра различных вариантов размещения для приложения WCF см. [размещение служб](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="e6af9-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6af9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e6af9-109">See Also</span></span>  
 [<span data-ttu-id="e6af9-110">Размещение</span><span class="sxs-lookup"><span data-stu-id="e6af9-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="e6af9-111">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="e6af9-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
