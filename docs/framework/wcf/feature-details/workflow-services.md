---
title: "Службы рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 043aa541e32077faf8141701a5ec7e8c0e711959
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="workflow-services"></a><span data-ttu-id="21e8e-102">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="21e8e-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="21e8e-103"> позволяет описать службу на основе рабочего процесса полностью декларативно на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="21e8e-103"> allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="21e8e-104">Рабочий процесс, реализующий службу, и описание конечных точек, предоставляемых службой, можно полностью определить на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="21e8e-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="21e8e-105">Подразделы, содержащиеся в этом разделе, подробно описывают модель программирования, декларативную поддержку создания служб.</span><span class="sxs-lookup"><span data-stu-id="21e8e-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21e8e-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="21e8e-106">In This Section</span></span>  
 [<span data-ttu-id="21e8e-107">Обзор служб рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="21e8e-107">Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services-overview.md)  
 <span data-ttu-id="21e8e-108">Описывает компоненты, участвующие в создании и размещении службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="21e8e-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="21e8e-109">Действия обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="21e8e-109">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 <span data-ttu-id="21e8e-110">Описывает действия, которые позволяют рабочим потокам отправлять или получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="21e8e-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="21e8e-111">Как: создание службы рабочего процесса с действиями обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="21e8e-111">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="21e8e-112">Описывает, как использовать действия обмена сообщениями для создания службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="21e8e-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="21e8e-113">Практическое руководство: Доступ к службе из приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="21e8e-113">How To: Access a Service From a Workflow Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="21e8e-114">Описывает, как вызвать службу из приложения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="21e8e-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="21e8e-115">Корреляции</span><span class="sxs-lookup"><span data-stu-id="21e8e-115">Correlation</span></span>](../../../../docs/framework/wcf/feature-details/correlation.md)  
 <span data-ttu-id="21e8e-116">Описывает, как корреляция сопоставляет сообщения друг с другом и с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="21e8e-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="21e8e-117">Обработка сообщений из внеочередной</span><span class="sxs-lookup"><span data-stu-id="21e8e-117">Out-of-Order Message Processing</span></span>](../../../../docs/framework/wcf/feature-details/out-of-order-message-processing.md)  
 <span data-ttu-id="21e8e-118">Описывает, как настроить службу для принятия несогласованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="21e8e-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="21e8e-119">Как: создание службы рабочего процесса, которая вызывает другую службу рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="21e8e-119">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 <span data-ttu-id="21e8e-120">Описывается синхронный вызов службы рабочего процесса из другой службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="21e8e-120">Describes how to synchronously call a workflow service from within another workflow service.</span></span>  
  
 [<span data-ttu-id="21e8e-121">Разработка служб рабочих процессов с первоочередным назначением контрактов</span><span class="sxs-lookup"><span data-stu-id="21e8e-121">Contract First Workflow Service Development</span></span>](../../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="21e8e-122">Описывает создание службы рабочих процессов на основе существующего контракта службы.</span><span class="sxs-lookup"><span data-stu-id="21e8e-122">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="21e8e-123">Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы</span><span class="sxs-lookup"><span data-stu-id="21e8e-123">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="21e8e-124">Предоставляет подробный пример создания службы рабочих процессов на основе существующего контракта.</span><span class="sxs-lookup"><span data-stu-id="21e8e-124">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="21e8e-125">Общие сведения о размещении служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="21e8e-125">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 <span data-ttu-id="21e8e-126">Описывает различные аспекты размещения службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="21e8e-126">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="21e8e-127">Использование контрактов в рабочем процессе</span><span class="sxs-lookup"><span data-stu-id="21e8e-127">Using Contracts in Workflow</span></span>](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  
 <span data-ttu-id="21e8e-128">Описывает различные типы контрактов и вывод контракта.</span><span class="sxs-lookup"><span data-stu-id="21e8e-128">Describes the different types of contracts and contract inference.</span></span>
