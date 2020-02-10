---
title: Образец обнаружения рабочего процесса
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: eafe031b71836eae8de5ce15cd669459c866e89f
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094765"
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="4c7d6-102">Образец обнаружения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="4c7d6-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="4c7d6-103">В этом образце показано, как сделать службу рабочего процесса обнаруживаемой, а также как создать настраиваемое действие кода, используемое для поиска определенной службы.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4c7d6-104">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="4c7d6-104">Demonstrates</span></span>  
 <span data-ttu-id="4c7d6-105">Действия по обнаружению и использование рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="4c7d6-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="4c7d6-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="4c7d6-106">Discussion</span></span>  
 <span data-ttu-id="4c7d6-107">В первой части образца служба рабочего процесса делается доступной для обнаружения с помощью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="4c7d6-108">Конфигурацию можно также использовать для правильного применения службы с настраиваемыми метаданными (такими как области).</span><span class="sxs-lookup"><span data-stu-id="4c7d6-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="4c7d6-109">На клиенте в образце используется настраиваемое действие кода, которое при помощи обнаружения осуществляет поиск службы, соответствующей конкретному контракту.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="4c7d6-110">Действие кода выводит URI, в дальнейшем используемый действием отправки.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4c7d6-111">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="4c7d6-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="4c7d6-112">В этом примере используются конечные точки HTTP, для выполнения которых должны быть нужны соответствующие списки ACL URL-адресов (см. Дополнительные сведения о [настройке HTTP и HTTPS](../feature-details/configuring-http-and-https.md) ).</span><span class="sxs-lookup"><span data-stu-id="4c7d6-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md) for details).</span></span> <span data-ttu-id="4c7d6-113">Нужные списки управления доступом будут добавлены после выполнения следующей команды в командной строке с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="4c7d6-114">Если оболочке не понимает формат переменной, замените домен и имя пользователя следующими аргументами.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-114">If your shell does not understand the variable format, substitute your Domain and Username for the following arguments.</span></span>  
  
     <span data-ttu-id="4c7d6-115">**netsh http add urlacl URL =http://+:8000/ пользователь =% домен%\\% UserName%**</span><span class="sxs-lookup"><span data-stu-id="4c7d6-115">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4c7d6-116">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4c7d6-117">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4c7d6-117">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="4c7d6-118">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4c7d6-119">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-119">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
