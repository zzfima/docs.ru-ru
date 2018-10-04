---
title: Общие сведения о размещении служб рабочих процессов
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: dbe271e30e9c4e98a52c01ffaa21de25c127c7ff
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48245110"
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="c9bb2-102">Общие сведения о размещении служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c9bb2-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="c9bb2-103">Для выполнения служб рабочего процесса они должны быть размещены.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="c9bb2-104">Класс <xref:System.ServiceModel.WorkflowServiceHost> представляет собой готовый узел размещения рабочих процессов, поддерживающий использование нескольких экземпляров, настройку и обмен сообщениями WCF (хотя от размещаемых рабочих процессов и не требуется обмена сообщениями).</span><span class="sxs-lookup"><span data-stu-id="c9bb2-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="c9bb2-105">Он также реализует сохраняемость, отслеживание и контроль за экземплярами через набор поведений службы.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="c9bb2-106">Как и класс WCF <xref:System.ServiceModel.ServiceHost>, класс <xref:System.ServiceModel.WorkflowServiceHost> может быть резидентным в любом управляемом приложении .NET или размещаться на веб-сервере IIS / WAS (в виде файла XAMLX).</span><span class="sxs-lookup"><span data-stu-id="c9bb2-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="c9bb2-107">В этом разделе описано размещение службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9bb2-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c9bb2-108">In This Section</span></span>  
 [<span data-ttu-id="c9bb2-109">Размещение служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c9bb2-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="c9bb2-110">Описывает размещение служб рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="c9bb2-111">Внутренние особенности размещения службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="c9bb2-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="c9bb2-112">Описывает, как объект <xref:System.ServiceModel.WorkflowServiceHost> обрабатывает входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="c9bb2-113">Расширяемость узла службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c9bb2-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="c9bb2-114">Описывает способы расширения функциональности узла службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="c9bb2-115">Конечная точка элемента управления рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="c9bb2-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="c9bb2-116">Описывает, как определить конечную точку, позволяющую создавать экземпляры рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>
  
 [<span data-ttu-id="c9bb2-117">Практическое руководство. Размещение службы рабочего процесса с помощью Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="c9bb2-117">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="c9bb2-118">Демонстрирует размещение существующей службы рабочего процесса в фабрике приложений Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-118">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="c9bb2-119">Настройка WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="c9bb2-119">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="c9bb2-120">Описывает управление сохраняемостью, отслеживанием, простоем и поведением необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="c9bb2-120">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c9bb2-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="c9bb2-121">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="c9bb2-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c9bb2-122">Related Sections</span></span>  
 [<span data-ttu-id="c9bb2-123">Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c9bb2-123">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
