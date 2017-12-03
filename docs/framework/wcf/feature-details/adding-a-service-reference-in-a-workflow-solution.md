---
title: "Добавление ссылки на службу в решение рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a80362f8cb7dce2853472b7f03c3586e33b8578
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a><span data-ttu-id="71b88-102">Добавление ссылки на службу в решение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="71b88-102">Adding a Service Reference in a Workflow Solution</span></span>
<span data-ttu-id="71b88-103">Добавление ссылки на службу в приложение рабочего процесса работает несколько иначе, чем обычное приложение WCF.</span><span class="sxs-lookup"><span data-stu-id="71b88-103">Adding a service reference in a workflow application works a little differently than a regular WCF application.</span></span> <span data-ttu-id="71b88-104">При выборе команды «Добавить ссылку на службу» и указании URL-адреса службы загружаются метаданные и создаются пользовательские действия, позволяющие вызывать службу WCF или службу рабочего процесса WCF, на которую была добавлена ссылка.</span><span class="sxs-lookup"><span data-stu-id="71b88-104">When you select Add Service Reference and specify the URL to the service the metadata is downloaded and custom activities are generated that allow you to call the WCF service or WCF workflow service you added a reference to.</span></span> <span data-ttu-id="71b88-105">После добавления ссылки на службу заново постройте решение, чтобы построить сформированные действия.</span><span class="sxs-lookup"><span data-stu-id="71b88-105">After adding a service reference, rebuild the solution so the generated activities are built.</span></span> <span data-ttu-id="71b88-106">После этого они отобразятся в области элементов конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="71b88-106">They will then appear in the workflow designer toolbox.</span></span> <span data-ttu-id="71b88-107">Тем не менее обратите внимание, что это будет работать только при добавлении ссылки на службу в пределах решения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="71b88-107">Note however, that this will only work if you are adding a service reference within a workflow solution.</span></span> <span data-ttu-id="71b88-108">Следующие веб-трансляции показано, как добавить ссылку на службу в других типов проектов: [вызова службы WCF из рабочего процесса в проекте веб-](http://go.microsoft.com/fwlink/?LinkId=207725).</span><span class="sxs-lookup"><span data-stu-id="71b88-108">The following web cast shows how to add a service reference in other types of projects: [Calling a WCF Service from a Workflow in a Web Project](http://go.microsoft.com/fwlink/?LinkId=207725).</span></span>  
  
 <span data-ttu-id="71b88-109">При добавлении двух или более ссылок на службы, которые содержат одинаковое имя операции, возникнет проблема.</span><span class="sxs-lookup"><span data-stu-id="71b88-109">Adding two or more service references to services that contain the same operation name will cause a problem.</span></span> <span data-ttu-id="71b88-110">Созданные действия будут вызывать только первую операцию службы.</span><span class="sxs-lookup"><span data-stu-id="71b88-110">The generated activities will call only the first service operation.</span></span> <span data-ttu-id="71b88-111">Для решения этой проблемы переименуйте операции служб, чтобы они отличались, или измените имя конфигурации конечной точки в каждом созданном действии.</span><span class="sxs-lookup"><span data-stu-id="71b88-111">To work around this issue rename the service operations so they are different or change the endpoint configuration name within each generated activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b88-112">См. также</span><span class="sxs-lookup"><span data-stu-id="71b88-112">See Also</span></span>  
 [<span data-ttu-id="71b88-113">Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="71b88-113">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="71b88-114">Как: создание службы рабочего процесса, которая вызывает другую службу рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="71b88-114">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 [<span data-ttu-id="71b88-115">Вызов службы WCF из рабочего процесса в веб-проект</span><span class="sxs-lookup"><span data-stu-id="71b88-115">Calling a WCF Service from a Workflow in a Web Project</span></span>](http://go.microsoft.com/fwlink/?LinkId=207725)
