---
title: Развертывание служб
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 684b781c568518cfb321d8021e4f7062e855e6aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798140"
---
# <a name="deploying-services"></a><span data-ttu-id="15546-102">Развертывание служб</span><span class="sxs-lookup"><span data-stu-id="15546-102">Deploying Services</span></span>
<span data-ttu-id="15546-103">В этом разделе описывается, как можно развернуть приложение Windows Communication Foundation (WCF) в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="15546-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="15546-104">Выбор среды размещения для приложения</span><span class="sxs-lookup"><span data-stu-id="15546-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="15546-105">Службы WCF предназначены для работы в любом процессе Windows, который поддерживает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="15546-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="15546-106">Для активации службы ее необходимо разместить в среде выполнения, которая создает эту службу и управляет ее контекстом и временем существования.</span><span class="sxs-lookup"><span data-stu-id="15546-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="15546-107">Варианты размещения могут быть самыми различными - от выполнения внутри простейшего консольного приложения до работы в серверных средах (таких как службы Windows, службы IIS) или внутри рабочего процесса, управляемого службой активации Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="15546-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="15546-108">Чтобы просмотреть различные варианты размещения для приложения WCF, см. раздел [службы хостинга](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="15546-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15546-109">См. также</span><span class="sxs-lookup"><span data-stu-id="15546-109">See also</span></span>

- [<span data-ttu-id="15546-110">Размещение</span><span class="sxs-lookup"><span data-stu-id="15546-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="15546-111">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="15546-111">Hosting Services</span></span>](../hosting-services.md)
