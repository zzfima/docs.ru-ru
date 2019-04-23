---
title: Развертывание служб
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 2c3cd17b597fafcd02b9155089bc583fafbc9dea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085768"
---
# <a name="deploying-services"></a><span data-ttu-id="2e0cb-102">Развертывание служб</span><span class="sxs-lookup"><span data-stu-id="2e0cb-102">Deploying Services</span></span>
<span data-ttu-id="2e0cb-103">В этом разделе описываются способы развертывания приложения в среде выполнения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2e0cb-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="2e0cb-104">Выбор среды размещения для приложения</span><span class="sxs-lookup"><span data-stu-id="2e0cb-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="2e0cb-105">Службы WCF, предназначены для выполнения в любом процессе Windows, который поддерживает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="2e0cb-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="2e0cb-106">Для активации службы ее необходимо разместить в среде выполнения, которая создает эту службу и управляет ее контекстом и временем существования.</span><span class="sxs-lookup"><span data-stu-id="2e0cb-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="2e0cb-107">Варианты размещения могут быть самыми различными - от выполнения внутри простейшего консольного приложения до работы в серверных средах (таких как службы Windows, службы IIS) или внутри рабочего процесса, управляемого службой активации Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="2e0cb-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="2e0cb-108">Для просмотра разных вариантов размещения для приложения WCF, см. в разделе [размещение служб](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e0cb-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0cb-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2e0cb-109">See also</span></span>

- [<span data-ttu-id="2e0cb-110">Размещение</span><span class="sxs-lookup"><span data-stu-id="2e0cb-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)
- [<span data-ttu-id="2e0cb-111">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="2e0cb-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
