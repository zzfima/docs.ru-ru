---
title: "Пользовательские критерии поиска"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2723929-8829-424d-8015-a37ba2ab4f68
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d49661ff91477f2f53d180a10ae1c9b3b632461f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="custom-find-criteria"></a><span data-ttu-id="6b122-102">Пользовательские критерии поиска</span><span class="sxs-lookup"><span data-stu-id="6b122-102">Custom Find Criteria</span></span>
<span data-ttu-id="6b122-103">В этом образце показано, как создать логику сопоставления пользовательских областей и реализовать пользовательскую службу обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6b122-103">This sample demonstrates how to create a custom scope match using logic and how to implement a custom discovery service.</span></span> <span data-ttu-id="6b122-104">Клиенты используют функции сопоставления пользовательских областей, чтобы расширить функции поиска, предоставляемые системой WCF Discovery.</span><span class="sxs-lookup"><span data-stu-id="6b122-104">Clients use custom scope matching functionality to refine and further build on top of the system-provided find functionality of WCF Discovery.</span></span> <span data-ttu-id="6b122-105">В этом образце реализован следующий сценарий.</span><span class="sxs-lookup"><span data-stu-id="6b122-105">The scenario this sample covers is as follows:</span></span>  
  
1.  <span data-ttu-id="6b122-106">Клиент ищет службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="6b122-106">A client is looking for a calculator service.</span></span>  
  
2.  <span data-ttu-id="6b122-107">Чтобы уточнить поиск, клиент должен использовать правило сопоставления пользовательских областей.</span><span class="sxs-lookup"><span data-stu-id="6b122-107">To refine its search, the client must use a custom scope matching rule.</span></span>  
  
3.  <span data-ttu-id="6b122-108">Согласно этому правилу, служба отвечает клиенту, если ее конечная точка совпадает с любой из областей, указанных клиентом.</span><span class="sxs-lookup"><span data-stu-id="6b122-108">According to this rule, a service responds back to the client if its endpoint matches any of the scopes specified by the client.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6b122-109">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="6b122-109">Demonstrates</span></span>  
  
-   <span data-ttu-id="6b122-110">Создание пользовательской службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6b122-110">Creating a custom discovery service.</span></span>  
  
-   <span data-ttu-id="6b122-111">Реализация сопоставления пользовательских областей по алгоритму.</span><span class="sxs-lookup"><span data-stu-id="6b122-111">Implementing a custom scope match by algorithm.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="6b122-112">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="6b122-112">Discussion</span></span>  
 <span data-ttu-id="6b122-113">Клиент выполняет поиск «Или» тип, соответствующий критериям.</span><span class="sxs-lookup"><span data-stu-id="6b122-113">The client is looking for "OR" type matching criteria.</span></span> <span data-ttu-id="6b122-114">Служба отвечает, если области в ее конечных точках совпадают с любыми из областей, предоставленных клиентом.</span><span class="sxs-lookup"><span data-stu-id="6b122-114">A service responds back if the scopes on its endpoints match any of the scopes provided by the client.</span></span> <span data-ttu-id="6b122-115">В этом случае клиент ищет службу калькулятора, любая из областей которой принадлежит следующему списку.</span><span class="sxs-lookup"><span data-stu-id="6b122-115">In this case, the client is looking for a calculator service that has any of the scopes in the following list:</span></span>  
  
1.  `net.tcp://Microsoft.Samples.Discovery/RedmondLocation`  
  
2.  `net.tcp://Microsoft.Samples.Discovery/SeattleLocation`  
  
3.  `net.tcp://Microsoft.Samples.Discovery/PortlandLocation`  
  
 <span data-ttu-id="6b122-116">Для этого клиент направляет службы в правило сопоставления пользовательских областей, передавая пользовательскую область по URI.</span><span class="sxs-lookup"><span data-stu-id="6b122-116">To accomplish this, the client directs services to use a custom scope matching rule by passing in a custom scope match by URI.</span></span> <span data-ttu-id="6b122-117">Чтобы упростить сопоставление пользовательских областей, служба должна использовать пользовательскую службу обнаружения, которая поддерживает правило сопоставления пользовательских областей и в которой реализована соответствующая логика сопоставления.</span><span class="sxs-lookup"><span data-stu-id="6b122-117">To facilitate the custom scope matching, the service must use a custom discovery service that understands the custom scope match rule and implements the associated matching logic.</span></span>  
  
 <span data-ttu-id="6b122-118">В клиентском проекте откройте файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="6b122-118">In the client project, open the Program.cs file.</span></span> <span data-ttu-id="6b122-119">Заметьте, что в поле `ScopeMatchBy` объекта `FindCriteria` задается определенный URI.</span><span class="sxs-lookup"><span data-stu-id="6b122-119">Note that the `ScopeMatchBy` field of the `FindCriteria` object is set to a specific URI.</span></span> <span data-ttu-id="6b122-120">Этот идентификатор отправляется в службу.</span><span class="sxs-lookup"><span data-stu-id="6b122-120">This identifier is sent to the service.</span></span> <span data-ttu-id="6b122-121">Если служба не поддерживает это правило, то она не обрабатывает клиентский запрос поиска.</span><span class="sxs-lookup"><span data-stu-id="6b122-121">If the service does not understand this rule, it ignores the client’s find request.</span></span>  
  
 <span data-ttu-id="6b122-122">Откройте проект службы.</span><span class="sxs-lookup"><span data-stu-id="6b122-122">Open the service project.</span></span> <span data-ttu-id="6b122-123">Для реализации пользовательской службы обнаружения используются три файла.</span><span class="sxs-lookup"><span data-stu-id="6b122-123">Three files are used to implement the Custom Discovery Service:</span></span>  
  
1.  <span data-ttu-id="6b122-124">**AsyncResult.cs**: это реализация `AsyncResult` , необходимые при использовании методов обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6b122-124">**AsyncResult.cs**: This is the implementation of the `AsyncResult` that is required by Discovery methods.</span></span>  
  
2.  <span data-ttu-id="6b122-125">**CustomDiscoveryService.cs**: этот файл реализует пользовательскую службу обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6b122-125">**CustomDiscoveryService.cs**: This file implements the custom discovery service.</span></span> <span data-ttu-id="6b122-126">В реализации расширяется класс <xref:System.ServiceModel.Discovery.DiscoveryService> и переопределяются необходимые методы.</span><span class="sxs-lookup"><span data-stu-id="6b122-126">The implementation extends the <xref:System.ServiceModel.Discovery.DiscoveryService> class and overrides the necessary methods.</span></span> <span data-ttu-id="6b122-127">Обратите внимание на реализацию метода <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b122-127">Note the implementation of the <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A> method.</span></span> <span data-ttu-id="6b122-128">Метод проверяет, задано ли клиентом правило сопоставления пользовательских областей.</span><span class="sxs-lookup"><span data-stu-id="6b122-128">The method checks to see whether the custom scope match by rule was specified by the client.</span></span> <span data-ttu-id="6b122-129">Это тот же пользовательский URI, который клиент указывал ранее.</span><span class="sxs-lookup"><span data-stu-id="6b122-129">This is the same custom URI that the client specified previously.</span></span> <span data-ttu-id="6b122-130">Если указано пользовательское правило, следует путь кода, в которой реализована логика сопоставления «Или».</span><span class="sxs-lookup"><span data-stu-id="6b122-130">If the custom rule is specified, the code path that implements the "OR" match logic is followed.</span></span>  
  
     <span data-ttu-id="6b122-131">Эта пользовательская логика проходит по всем областям в каждой из конечных точек, входящих в службу.</span><span class="sxs-lookup"><span data-stu-id="6b122-131">This custom logic goes through all of the scopes on each of the endpoints that the service has.</span></span> <span data-ttu-id="6b122-132">Если области конечной точки совпадают с любыми из областей, указанных клиентом, служба обнаружения добавляет конечную точку в ответ, который отправляется обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="6b122-132">If any of the endpoint's scopes match any of the scopes provided by the client, the discovery service adds that endpoint to the response that is sent back to the client.</span></span>  
  
3.  <span data-ttu-id="6b122-133">**CustomDiscoveryExtension.cs**: последний шаг в реализации службы обнаружения является подключение этой реализации пользовательской службы обнаружения к узлу службы.</span><span class="sxs-lookup"><span data-stu-id="6b122-133">**CustomDiscoveryExtension.cs**: The last step in implementing the discovery service is to connect this implementation of the custom discover service to the service host.</span></span> <span data-ttu-id="6b122-134">Здесь используется вспомогательный класс `CustomDiscoveryExtension`.</span><span class="sxs-lookup"><span data-stu-id="6b122-134">The helper class used here is the `CustomDiscoveryExtension` class.</span></span> <span data-ttu-id="6b122-135">Этот класс расширяет класс <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension>.</span><span class="sxs-lookup"><span data-stu-id="6b122-135">This class extends the <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension> class.</span></span> <span data-ttu-id="6b122-136">Пользователь должен переопределить метод <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension.GetDiscoveryService%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b122-136">The user must override the <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension.GetDiscoveryService%2A> method.</span></span> <span data-ttu-id="6b122-137">В этом случае метод возвращает экземпляр пользовательской службы обнаружения, который был создан ранее.</span><span class="sxs-lookup"><span data-stu-id="6b122-137">In this case, the method returns an instance of the custom discovery service that was created before.</span></span> <span data-ttu-id="6b122-138">`PublishedEndpoints` - коллекция <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, которая содержит все конечные точки приложения, добавленные в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="6b122-138">`PublishedEndpoints` is a <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> that contains all of the application endpoints that are added to the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="6b122-139">Пользовательская служба обнаружения использует эту коллекцию для заполнения внутреннего списка.</span><span class="sxs-lookup"><span data-stu-id="6b122-139">The custom discovery service uses this to populate its internal list.</span></span> <span data-ttu-id="6b122-140">Пользователь может добавлять и другие метаданные конечных точек.</span><span class="sxs-lookup"><span data-stu-id="6b122-140">A user can to add other endpoint metadata as well.</span></span>  
  
 <span data-ttu-id="6b122-141">Наконец, откройте файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="6b122-141">Lastly, open Program.cs.</span></span> <span data-ttu-id="6b122-142">Заметьте, что в узел добавляются объекты <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> и `CustomDiscoveryExtension`.</span><span class="sxs-lookup"><span data-stu-id="6b122-142">Note that both the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and `CustomDiscoveryExtension` are added to the host.</span></span> <span data-ttu-id="6b122-143">После этого, когда в узле есть конечная точка, через которую принимаются сообщения обнаружения, приложение может использовать пользовательскую службу обнаружения.</span><span class="sxs-lookup"><span data-stu-id="6b122-143">Once this is done and the host has an endpoint over which to receive discovery messages, the application can use the custom discovery service.</span></span>  
  
 <span data-ttu-id="6b122-144">Заметьте, что клиенту удается найти службу, не зная ее адреса.</span><span class="sxs-lookup"><span data-stu-id="6b122-144">Observe that the client is able to find the service without knowing its address.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6b122-145">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="6b122-145">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6b122-146">Откройте решение, содержащее проект.</span><span class="sxs-lookup"><span data-stu-id="6b122-146">Open the solution that contains the project.</span></span>  
  
2.  <span data-ttu-id="6b122-147">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="6b122-147">Build the project.</span></span>  
  
3.  <span data-ttu-id="6b122-148">Запустите приложение службы.</span><span class="sxs-lookup"><span data-stu-id="6b122-148">Run the service application.</span></span>  
  
4.  <span data-ttu-id="6b122-149">Запустите клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="6b122-149">Run the client application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b122-150">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6b122-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6b122-151">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6b122-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6b122-152">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b122-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6b122-153">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6b122-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\CustomFindCriteria`
