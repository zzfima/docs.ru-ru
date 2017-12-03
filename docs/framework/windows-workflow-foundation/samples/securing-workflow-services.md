---
title: "Защита служб рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cd7620186ed51110a32e251d5239c85bb90e0f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="securing-workflow-services"></a><span data-ttu-id="b9d47-102">Защита служб рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="b9d47-102">Securing Workflow Services</span></span>
<span data-ttu-id="b9d47-103">В образце безопасной службы рабочего процесса демонстрируются следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="b9d47-103">The Secured Workflow Service sample shows the following procedures:</span></span>  
  
-   <span data-ttu-id="b9d47-104">Создание базовой службы рабочего процесса с помощью действий <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="b9d47-104">Creating a basic workflow service using the <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
-   <span data-ttu-id="b9d47-105">Использование конфигурации [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для определения защищенных конечных точек для использования службой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b9d47-105">Using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] configuration to define secure endpoints for use by the workflow service.</span></span>  
  
-   <span data-ttu-id="b9d47-106">Создание утверждений внутри настраиваемой политики с использованием <xref:System.ServiceModel.ServiceAuthorizationManager> для проверки утверждений.</span><span class="sxs-lookup"><span data-stu-id="b9d47-106">Creating claims inside a custom policy and using the <xref:System.ServiceModel.ServiceAuthorizationManager> to validate claims.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b9d47-107">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="b9d47-107">Demonstrates</span></span>  
 <span data-ttu-id="b9d47-108">Использование безопасности WCF для защиты взаимодействия между клиентом и службой рабочего процесса, авторизация на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="b9d47-108">Using WCF security to secure communication between client and Workflow service, Claims based authorization</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b9d47-109">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="b9d47-109">Discussion</span></span>  
 <span data-ttu-id="b9d47-110">В этом образце демонстрируется использование инфраструктуры безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для защиты службы рабочего процесса таким же образом, как и для обычной службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9d47-110">This sample demonstrates the use of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security infrastructure to secure a workflow service just like you would with a normal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="b9d47-111">Конкретно, в примере для авторизации используется пользовательское утверждение.</span><span class="sxs-lookup"><span data-stu-id="b9d47-111">Specifically, it uses a custom claim for authorization.</span></span> <span data-ttu-id="b9d47-112">В этом случае используется <xref:System.ServiceModel.WSHttpBinding> и безопасность режима сообщений с учетными данными Windows.</span><span class="sxs-lookup"><span data-stu-id="b9d47-112">In this case, it uses <xref:System.ServiceModel.WSHttpBinding> and message mode security with Windows credentials.</span></span>  
  
 <span data-ttu-id="b9d47-113">Настраиваемая политика <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) проверяет имя пользователя Windows клиента и анализирует конкретный символ.</span><span class="sxs-lookup"><span data-stu-id="b9d47-113">The custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) checks the client's Windows username and for a specific character.</span></span> <span data-ttu-id="b9d47-114">Если этот символ присутствует, он создает и добавляет утверждение в контекст <xref:System.IdentityModel.Policy.EvaluationContext>.</span><span class="sxs-lookup"><span data-stu-id="b9d47-114">If that character is present, it creates and adds the claim to the <xref:System.IdentityModel.Policy.EvaluationContext>.</span></span> <span data-ttu-id="b9d47-115">Выполняя это, настраиваемая политика делает утверждение, что клиент имеет этот символ в имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="b9d47-115">By doing this, the custom policy is making the statement that the client has this character in the username.</span></span> <span data-ttu-id="b9d47-116">Это утверждение может запрашиваться в течение времени существования вызова.</span><span class="sxs-lookup"><span data-stu-id="b9d47-116">This claim can be queried throughout the lifetime of the call.</span></span> <span data-ttu-id="b9d47-117">Этот символ можно найти в `Constants.cs`.</span><span class="sxs-lookup"><span data-stu-id="b9d47-117">You can find that character in `Constants.cs`.</span></span>  
  
 <span data-ttu-id="b9d47-118">Политика авторизации ищет утверждение внутри `SecureWorkFlowAuthZManager`.</span><span class="sxs-lookup"><span data-stu-id="b9d47-118">The authorization policy looks for the claim inside the `SecureWorkFlowAuthZManager`.</span></span> <span data-ttu-id="b9d47-119">Если она его находит, она возвращает значение `true` и разрешает продолжение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b9d47-119">If it finds it, it returns `true` and allow the workflow to proceed.</span></span> <span data-ttu-id="b9d47-120">В противном случает она возвращает значение `false`, которое вызывает возврат клиенту сообщения «Отказано в доступе».</span><span class="sxs-lookup"><span data-stu-id="b9d47-120">Otherwise, it returns `false`, which causes an 'Access Denied' message to be returned to the client.</span></span> <span data-ttu-id="b9d47-121">Другие утверждения присутствуют в контексте и могут также проверяться внутри `SecureWorkFlowAuthZManager`.</span><span class="sxs-lookup"><span data-stu-id="b9d47-121">Other claims are present in the context and can be examined as well inside the `SecureWorkFlowAuthZManager`.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="b9d47-122">Запуск образца</span><span class="sxs-lookup"><span data-stu-id="b9d47-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="b9d47-123">Запустите среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="b9d47-123">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="b9d47-124">Загрузка SecuringWorkflowServices.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9d47-124">Load SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="b9d47-125">Для компиляции решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="b9d47-125">Press CTRL+SHIFT+B to compile the solution.</span></span>  
  
4.  <span data-ttu-id="b9d47-126">Установите проект Service в качестве проекта для запуска решения.</span><span class="sxs-lookup"><span data-stu-id="b9d47-126">Set the Service project as the start-up project for the solution.</span></span>  
  
5.  <span data-ttu-id="b9d47-127">Чтобы запустить службу без отладки, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="b9d47-127">Press CTRL+F5 to start the service without debugging.</span></span>  
  
6.  <span data-ttu-id="b9d47-128">Установите проект Client в качестве проекта для запуска решения.</span><span class="sxs-lookup"><span data-stu-id="b9d47-128">Set the Client project as the start-up project for the solution.</span></span>  
  
7.  <span data-ttu-id="b9d47-129">Чтобы запустить клиент без отладки, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="b9d47-129">Press CTRL+F5 to start the client without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b9d47-130">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b9d47-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b9d47-131">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b9d47-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b9d47-132">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9d47-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b9d47-133">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b9d47-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
