---
title: "Общие сведения о размещении служб рабочих процессов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c38cd352eb860982b9b1e3aa32daa7aeeee9ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="e53e0-102">Общие сведения о размещении служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e53e0-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="e53e0-103">Для выполнения служб рабочего процесса они должны быть размещены.</span><span class="sxs-lookup"><span data-stu-id="e53e0-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="e53e0-104">Класс <xref:System.ServiceModel.WorkflowServiceHost> представляет собой готовый узел размещения рабочих процессов, поддерживающий использование нескольких экземпляров, настройку и обмен сообщениями WCF (хотя от размещаемых рабочих процессов и не требуется обмена сообщениями).</span><span class="sxs-lookup"><span data-stu-id="e53e0-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="e53e0-105">Он также реализует сохраняемость, отслеживание и контроль за экземплярами через набор поведений службы.</span><span class="sxs-lookup"><span data-stu-id="e53e0-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="e53e0-106">Как и класс WCF <xref:System.ServiceModel.ServiceHost>, класс <xref:System.ServiceModel.WorkflowServiceHost> может быть резидентным в любом управляемом приложении .NET или размещаться на веб-сервере IIS / WAS (в виде файла XAMLX).</span><span class="sxs-lookup"><span data-stu-id="e53e0-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="e53e0-107">В этом разделе описано размещение службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e53e0-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e53e0-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="e53e0-108">In This Section</span></span>  
 [<span data-ttu-id="e53e0-109">Размещение служб рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e53e0-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="e53e0-110">Описывает размещение служб рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e53e0-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="e53e0-111">Внутренние особенности размещения службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e53e0-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="e53e0-112">Описывает, как объект <xref:System.ServiceModel.WorkflowServiceHost> обрабатывает входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="e53e0-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="e53e0-113">Расширяемость узла службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e53e0-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="e53e0-114">Описывает способы расширения функциональности узла службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e53e0-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="e53e0-115">Конечная точка управления рабочим процессом</span><span class="sxs-lookup"><span data-stu-id="e53e0-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="e53e0-116">Описывает, как определить конечную точку, позволяющую создавать экземпляры рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="e53e0-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>  
  
 [<span data-ttu-id="e53e0-117">Как: разместить не являющийся службой рабочий процесс в службах IIS</span><span class="sxs-lookup"><span data-stu-id="e53e0-117">How to: Host a non-service workflow in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 <span data-ttu-id="e53e0-118">Демонстрирует размещение в службах IIS рабочего процесса, который не является службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e53e0-118">Demonstrates hosting a workflow that is not a workflow service in IIS.</span></span>  
  
 [<span data-ttu-id="e53e0-119">Как: размещение службы рабочего процесса с помощью Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="e53e0-119">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="e53e0-120">Демонстрирует размещение существующей службы рабочего процесса в фабрике приложений Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e53e0-120">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="e53e0-121">Настройка WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="e53e0-121">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="e53e0-122">Описывает управление сохраняемостью, отслеживанием, простоем и поведением необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="e53e0-122">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e53e0-123">Ссылка</span><span class="sxs-lookup"><span data-stu-id="e53e0-123">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="e53e0-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e53e0-124">Related Sections</span></span>  
 [<span data-ttu-id="e53e0-125">Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e53e0-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
