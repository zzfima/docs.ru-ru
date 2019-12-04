---
title: Корреляция запросов сообщений LINQ
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: a4b0ed058cfe8d3d487342c9feefdf1b1efe07c8
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715584"
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="f358b-102">Корреляция запросов сообщений LINQ</span><span class="sxs-lookup"><span data-stu-id="f358b-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="f358b-103">Этот образец демонстрирует, как выполнять корреляцию на основе содержимого с использованием пользовательской реализации <xref:System.ServiceModel.Dispatcher.MessageQuery> (в отличие от системной реализации <xref:System.ServiceModel.XPathMessageQuery>).</span><span class="sxs-lookup"><span data-stu-id="f358b-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="f358b-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="f358b-104">Demonstrates</span></span>  
 <span data-ttu-id="f358b-105">Пользовательская корреляция <xref:System.ServiceModel.Dispatcher.MessageQuery> на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="f358b-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="f358b-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="f358b-106">Discussion</span></span>  
 <span data-ttu-id="f358b-107">Этот образец показывает, как выполняется расширение базового класса <xref:System.ServiceModel.Dispatcher.MessageQuery> с целью корреляции.</span><span class="sxs-lookup"><span data-stu-id="f358b-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="f358b-108">Пользовательская реализация `LinqMessageQuery` позволяет пользователям выдавать XName для поиска внутри сообщения с использованием XLinq.</span><span class="sxs-lookup"><span data-stu-id="f358b-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="f358b-109">Данные, полученные в результате выполнения запроса, используются для формирования ключа корреляции с целью перенаправления сообщений в соответствующий экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f358b-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f358b-110">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="f358b-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="f358b-111">В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP.</span><span class="sxs-lookup"><span data-stu-id="f358b-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="f358b-112">Чтобы выполнить этот пример, необходимо добавить соответствующие списки ACL URL-адресов (см. Дополнительные сведения о [настройке HTTP и HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) ), запустив Visual Studio от имени администратора или выполнив следующую команду в командной строке с повышенными привилегиями, чтобы добавить соответствующие списки ACL.</span><span class="sxs-lookup"><span data-stu-id="f358b-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="f358b-113">Убедитесь, что подставлены нужный домен и имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="f358b-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="f358b-114">После добавления списков управления доступом по URL-адресу выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f358b-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="f358b-115">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="f358b-115">Build the solution.</span></span>  
  
    2. <span data-ttu-id="f358b-116">Задайте несколько проектов запуска, щелкнув решение правой кнопкой мыши и выбрав пункт **задать запускаемые проекты**.</span><span class="sxs-lookup"><span data-stu-id="f358b-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="f358b-117">Добавьте **службу** и **клиент** (в этом порядке) в качестве нескольких запускаемых проектов.</span><span class="sxs-lookup"><span data-stu-id="f358b-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3. <span data-ttu-id="f358b-118">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="f358b-118">Run the application.</span></span> <span data-ttu-id="f358b-119">На консоль клиентского приложения выводится рабочий процесс, вначале отправляющий заказ, затем получающий идентификатор заказа на покупку и, наконец, подтверждающий заказ.</span><span class="sxs-lookup"><span data-stu-id="f358b-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="f358b-120">В окне службы будут выведены сведения об обрабатываемых запросах.</span><span class="sxs-lookup"><span data-stu-id="f358b-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f358b-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f358b-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f358b-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f358b-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="f358b-123">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="f358b-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f358b-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f358b-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
