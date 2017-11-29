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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8eeb446687b2aa75c90ec02995319fc5a0cbebf3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-services"></a><span data-ttu-id="cdf47-102">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cdf47-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="cdf47-103"> позволяет описать службу на основе рабочего процесса полностью декларативно на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="cdf47-103"> allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="cdf47-104">Рабочий процесс, реализующий службу, и описание конечных точек, предоставляемых службой, можно полностью определить на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="cdf47-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="cdf47-105">Подразделы, содержащиеся в этом разделе, подробно описывают модель программирования, декларативную поддержку создания служб.</span><span class="sxs-lookup"><span data-stu-id="cdf47-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cdf47-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="cdf47-106">In This Section</span></span>  
 [<span data-ttu-id="cdf47-107">Обзор служб рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cdf47-107">Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services-overview.md)  
 <span data-ttu-id="cdf47-108">Описывает компоненты, участвующие в создании и размещении службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cdf47-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="cdf47-109">Действия обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="cdf47-109">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 <span data-ttu-id="cdf47-110">Описывает действия, которые позволяют рабочим потокам отправлять или получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="cdf47-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="cdf47-111">Как: создание службы рабочего процесса с действиями обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="cdf47-111">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="cdf47-112">Описывает, как использовать действия обмена сообщениями для создания службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cdf47-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="cdf47-113">Практическое руководство: Доступ к службе из приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cdf47-113">How To: Access a Service From a Workflow Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="cdf47-114">Описывает, как вызвать службу из приложения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cdf47-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="cdf47-115">Корреляции</span><span class="sxs-lookup"><span data-stu-id="cdf47-115">Correlation</span></span>](../../../../docs/framework/wcf/feature-details/correlation.md)  
 <span data-ttu-id="cdf47-116">Описывает, как корреляция сопоставляет сообщения друг с другом и с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="cdf47-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="cdf47-117">Обработка сообщений из внеочередной</span><span class="sxs-lookup"><span data-stu-id="cdf47-117">Out-of-Order Message Processing</span></span>](../../../../docs/framework/wcf/feature-details/out-of-order-message-processing.md)  
 <span data-ttu-id="cdf47-118">Описывает, как настроить службу для принятия несогласованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="cdf47-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="cdf47-119">Как: создание службы рабочего процесса, которая вызывает другую службу рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="cdf47-119">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 <span data-ttu-id="cdf47-120">Описывается синхронный вызов службы рабочего процесса из другой службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cdf47-120">Describes how to synchronously call a workflow service from within another workflow service.</span></span>  
  
 [<span data-ttu-id="cdf47-121">Разработка служб рабочих процессов с первоочередным назначением контрактов</span><span class="sxs-lookup"><span data-stu-id="cdf47-121">Contract First Workflow Service Development</span></span>](../../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="cdf47-122">Описывает создание службы рабочих процессов на основе существующего контракта службы.</span><span class="sxs-lookup"><span data-stu-id="cdf47-122">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="cdf47-123">Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы</span><span class="sxs-lookup"><span data-stu-id="cdf47-123">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="cdf47-124">Предоставляет подробный пример создания службы рабочих процессов на основе существующего контракта.</span><span class="sxs-lookup"><span data-stu-id="cdf47-124">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="cdf47-125">Общие сведения о размещении служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="cdf47-125">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 <span data-ttu-id="cdf47-126">Описывает различные аспекты размещения службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cdf47-126">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="cdf47-127">Использование контрактов в рабочем процессе</span><span class="sxs-lookup"><span data-stu-id="cdf47-127">Using Contracts in Workflow</span></span>](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  
 <span data-ttu-id="cdf47-128">Описывает различные типы контрактов и вывод контракта.</span><span class="sxs-lookup"><span data-stu-id="cdf47-128">Describes the different types of contracts and contract inference.</span></span>
