---
title: "Образец асинхронной операции Find"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a793945906bb1a106916d59ff07ea813f38469d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-find-sample"></a><span data-ttu-id="d71b0-102">Образец асинхронной операции Find</span><span class="sxs-lookup"><span data-stu-id="d71b0-102">Asynchronous Find Sample</span></span>
<span data-ttu-id="d71b0-103">Этот образец показывает, как использовать асинхронную операцию поиска из клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="d71b0-103">This sample shows how to use the asynchronous find operation from a client application.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="d71b0-104">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="d71b0-104">Sample Details</span></span>  
 <span data-ttu-id="d71b0-105">Преимущества такого конструктивного решения в том, что клиент асинхронно уведомляется о конечных точках, найденных в результате выполнения поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="d71b0-105">The benefit of following this design pattern is that the client is notified asynchronously of the endpoints located as a result of the find request.</span></span> <span data-ttu-id="d71b0-106">Чтобы увидеть, как это происходит, откройте файл Client.cs.</span><span class="sxs-lookup"><span data-stu-id="d71b0-106">To see how this works, open the Client.cs file.</span></span> <span data-ttu-id="d71b0-107">Обратите внимание, что объект <xref:System.ServiceModel.Discovery.DiscoveryClient> имеет два делегата, подключенные к обработчикам событий.</span><span class="sxs-lookup"><span data-stu-id="d71b0-107">Note the <xref:System.ServiceModel.Discovery.DiscoveryClient> object has two delegates attached to its event handlers.</span></span> <span data-ttu-id="d71b0-108">Один из делегатов вызывается при возникновении события <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>, а другой - при каждом возникновении события <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.</span><span class="sxs-lookup"><span data-stu-id="d71b0-108">One delegate is called when a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is raised and another is called each time a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> event is raised.</span></span> <span data-ttu-id="d71b0-109">Образец показывает, как можно использовать этот шаблон в собственном приложении.</span><span class="sxs-lookup"><span data-stu-id="d71b0-109">The sample shows how you can utilize this pattern in your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d71b0-110">Образец использует конечные точки HTTP, а для запуска ему понадобятся соответствующие URL ACL.</span><span class="sxs-lookup"><span data-stu-id="d71b0-110">This sample uses HTTP endpoints and to run, proper URL ACLs must be added.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="d71b0-111">[Настройка HTTP и HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="d71b0-111"> [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="d71b0-112">Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="d71b0-112">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="d71b0-113">Если команда не работает, следует указать домен и имя пользователя в следующих аргументах.</span><span class="sxs-lookup"><span data-stu-id="d71b0-113">You may want to substitute your domain and username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d71b0-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="d71b0-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d71b0-115">Откройте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] файл AsyncFind.sln.</span><span class="sxs-lookup"><span data-stu-id="d71b0-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the AsyncFind.sln.</span></span>  
  
2.  <span data-ttu-id="d71b0-116">Чтобы построить решение, нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="d71b0-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="d71b0-117">Откройте командную строку [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], перейдите в каталог \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug или \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug и запустите файл Service.exe.</span><span class="sxs-lookup"><span data-stu-id="d71b0-117">Open a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug or \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug directory and run Service.exe.</span></span>  
  
4.  <span data-ttu-id="d71b0-118">После запуска службы перейдите в каталог \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug или WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug и запустите файл Client.exe.</span><span class="sxs-lookup"><span data-stu-id="d71b0-118">After the service has started, navigate to the \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug or WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug directory and run Client.exe.</span></span>  
  
5.  <span data-ttu-id="d71b0-119">Обратите внимание, что клиент может найти и вызвать службу.</span><span class="sxs-lookup"><span data-stu-id="d71b0-119">Observe the client is able to locate and call the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d71b0-120">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d71b0-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d71b0-121">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d71b0-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d71b0-122">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d71b0-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d71b0-123">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d71b0-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a><span data-ttu-id="d71b0-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d71b0-124">See Also</span></span>
