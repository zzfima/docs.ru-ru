---
title: "Корреляция запросов сообщений LINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 124f76012f342eff9b11a7208df1103cded3843c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="21a27-102">Корреляция запросов сообщений LINQ</span><span class="sxs-lookup"><span data-stu-id="21a27-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="21a27-103">Этот образец демонстрирует, как выполнять корреляцию на основе содержимого с использованием пользовательской реализации <xref:System.ServiceModel.Dispatcher.MessageQuery> (в отличие от системной реализации <xref:System.ServiceModel.XPathMessageQuery>).</span><span class="sxs-lookup"><span data-stu-id="21a27-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="21a27-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="21a27-104">Demonstrates</span></span>  
 <span data-ttu-id="21a27-105">Пользовательская корреляция <xref:System.ServiceModel.Dispatcher.MessageQuery> на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="21a27-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="21a27-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="21a27-106">Discussion</span></span>  
 <span data-ttu-id="21a27-107">Этот образец показывает, как выполняется расширение базового класса <xref:System.ServiceModel.Dispatcher.MessageQuery> с целью корреляции.</span><span class="sxs-lookup"><span data-stu-id="21a27-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="21a27-108">Пользовательская реализация `LinqMessageQuery` позволяет пользователям выдавать XName для поиска внутри сообщения с использованием XLinq.</span><span class="sxs-lookup"><span data-stu-id="21a27-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="21a27-109">Данные, полученные в результате выполнения запроса, используются для формирования ключа корреляции с целью перенаправления сообщений в соответствующий экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="21a27-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="21a27-110">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="21a27-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="21a27-111">В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP.</span><span class="sxs-lookup"><span data-stu-id="21a27-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="21a27-112">Для запуска этого примера, соответствующие URL ACL, необходимо добавить (см. [Настройка протоколов HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) подробные сведения), запустив Visual Studio от имени администратора, или, выполнив следующую команду в командной строке с повышенными привилегиями, чтобы добавить нужные списки управления доступом.</span><span class="sxs-lookup"><span data-stu-id="21a27-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="21a27-113">Убедитесь, что подставлены нужный домен и имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="21a27-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  <span data-ttu-id="21a27-114">После добавления списков управления доступом по URL-адресу выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="21a27-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1.  <span data-ttu-id="21a27-115">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="21a27-115">Build the solution.</span></span>  
  
    2.  <span data-ttu-id="21a27-116">Задайте несколько запускаемых проектов, щелкните правой кнопкой мыши решение и выбрав **назначить запускаемые проекты**.</span><span class="sxs-lookup"><span data-stu-id="21a27-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="21a27-117">Добавить **службы** и **клиента** (в указанном порядке) в качестве запускаемых проектов.</span><span class="sxs-lookup"><span data-stu-id="21a27-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3.  <span data-ttu-id="21a27-118">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="21a27-118">Run the application.</span></span> <span data-ttu-id="21a27-119">На консоль клиентского приложения выводится рабочий процесс, вначале отправляющий заказ, затем получающий идентификатор заказа на покупку и, наконец, подтверждающий заказ.</span><span class="sxs-lookup"><span data-stu-id="21a27-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="21a27-120">В окне службы будут выведены сведения об обрабатываемых запросах.</span><span class="sxs-lookup"><span data-stu-id="21a27-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="21a27-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="21a27-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="21a27-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="21a27-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="21a27-123">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21a27-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="21a27-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="21a27-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
