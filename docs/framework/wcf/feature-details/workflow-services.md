---
title: Службы рабочего процесса
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: e7295041fe4b17e7e2b1560704badf20992d4b92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929705"
---
# <a name="workflow-services"></a><span data-ttu-id="7c708-102">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7c708-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="7c708-103">позволяет описать службу на основе рабочего процесса полностью декларативно на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="7c708-103">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="7c708-104">Рабочий процесс, реализующий службу, и описание конечных точек, предоставляемых службой, можно полностью определить на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="7c708-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="7c708-105">Подразделы, содержащиеся в этом разделе, подробно описывают модель программирования, декларативную поддержку создания служб.</span><span class="sxs-lookup"><span data-stu-id="7c708-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c708-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7c708-106">In This Section</span></span>  
 [<span data-ttu-id="7c708-107">Общие сведения о службах рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7c708-107">Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services-overview.md)  
 <span data-ttu-id="7c708-108">Описывает компоненты, участвующие в создании и размещении службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7c708-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="7c708-109">Действия обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="7c708-109">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 <span data-ttu-id="7c708-110">Описывает действия, которые позволяют рабочим потокам отправлять или получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="7c708-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="7c708-111">Практическое руководство. Создание службы рабочего процесса с помощью действий обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="7c708-111">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="7c708-112">Описывает, как использовать действия обмена сообщениями для создания службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7c708-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="7c708-113">Практическое руководство. Доступ к службе из приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7c708-113">How To: Access a Service From a Workflow Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="7c708-114">Описывает, как вызвать службу из приложения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7c708-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="7c708-115">Корреляция</span><span class="sxs-lookup"><span data-stu-id="7c708-115">Correlation</span></span>](../../../../docs/framework/wcf/feature-details/correlation.md)  
 <span data-ttu-id="7c708-116">Описывает, как корреляция сопоставляет сообщения друг с другом и с экземплярами.</span><span class="sxs-lookup"><span data-stu-id="7c708-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="7c708-117">Обработка неупорядоченных сообщений</span><span class="sxs-lookup"><span data-stu-id="7c708-117">Out-of-Order Message Processing</span></span>](../../../../docs/framework/wcf/feature-details/out-of-order-message-processing.md)  
 <span data-ttu-id="7c708-118">Описывает, как настроить службу для принятия несогласованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="7c708-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="7c708-119">Разработка служб рабочих процессов с первоочередным назначением контрактов</span><span class="sxs-lookup"><span data-stu-id="7c708-119">Contract First Workflow Service Development</span></span>](../../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="7c708-120">Описывает создание службы рабочих процессов на основе существующего контракта службы.</span><span class="sxs-lookup"><span data-stu-id="7c708-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="7c708-121">Практическое руководство. Создание службы рабочего процесса, который использует существующий контракт службы</span><span class="sxs-lookup"><span data-stu-id="7c708-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="7c708-122">Предоставляет подробный пример создания службы рабочих процессов на основе существующего контракта.</span><span class="sxs-lookup"><span data-stu-id="7c708-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="7c708-123">Общие сведения о размещении служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7c708-123">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 <span data-ttu-id="7c708-124">Описывает различные аспекты размещения службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7c708-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="7c708-125">Использование контрактов в рабочих процессах</span><span class="sxs-lookup"><span data-stu-id="7c708-125">Using Contracts in Workflow</span></span>](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  
 <span data-ttu-id="7c708-126">Описывает различные типы контрактов и вывод контракта.</span><span class="sxs-lookup"><span data-stu-id="7c708-126">Describes the different types of contracts and contract inference.</span></span>
