---
title: "Образец обнаружения рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f778fead0e09be36ca2a829dde9cf906f4fcaa9f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="d2234-102">Образец обнаружения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d2234-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="d2234-103">В этом образце показано, как сделать службу рабочего процесса обнаруживаемой, а также как создать настраиваемое действие кода, используемое для поиска определенной службы.</span><span class="sxs-lookup"><span data-stu-id="d2234-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d2234-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="d2234-104">Demonstrates</span></span>  
 <span data-ttu-id="d2234-105">Действия по обнаружению и использование рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d2234-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="d2234-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="d2234-106">Discussion</span></span>  
 <span data-ttu-id="d2234-107">В первой части образца служба рабочего процесса делается доступной для обнаружения с помощью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2234-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="d2234-108">Конфигурацию можно также использовать для правильного применения службы с настраиваемыми метаданными (такими как области).</span><span class="sxs-lookup"><span data-stu-id="d2234-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="d2234-109">На клиенте в образце используется настраиваемое действие кода, которое при помощи обнаружения осуществляет поиск службы, соответствующей конкретному контракту.</span><span class="sxs-lookup"><span data-stu-id="d2234-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="d2234-110">Действие кода выводит URI, в дальнейшем используемый действием отправки.</span><span class="sxs-lookup"><span data-stu-id="d2234-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d2234-111">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="d2234-111">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d2234-112">Этот образец использует конечные точки HTTP, который должен иметь соответствующие списки управления доступом URL-адрес для запуска (см. [Настройка протоколов HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) подробные сведения).</span><span class="sxs-lookup"><span data-stu-id="d2234-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details).</span></span> <span data-ttu-id="d2234-113">Нужные списки управления доступом будут добавлены после выполнения следующей команды в командной строке с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d2234-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="d2234-114">Если оболочка не распознает формат переменной, замените домен и имя пользователя в следующих аргументах.</span><span class="sxs-lookup"><span data-stu-id="d2234-114">Substitute your Domain and Username for the following arguments if your shell does not understand the variable format.</span></span>  
  
     <span data-ttu-id="d2234-115">**добавить urlacl url-адрес Netsh http = http: / / +: 8000 / пользователь = % DOMAIN %\\% UserName %**</span><span class="sxs-lookup"><span data-stu-id="d2234-115">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2234-116">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d2234-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d2234-117">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d2234-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d2234-118">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2234-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d2234-119">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d2234-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
