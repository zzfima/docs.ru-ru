---
title: Доступ к службе из веб-браузера (краткое руководство по службе данных WCF)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c9ae96facd79ae3d268c630ff7bf8adf411eb775
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="d4b4b-102">Доступ к службе из веб-браузера (краткое руководство по службе данных WCF)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>
<span data-ttu-id="d4b4b-103">В этой задаче мы запустим службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] из Visual Studio и дополнительно отключим чтение канала в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-103">In this task, you will start the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="d4b4b-104">Вам будет затем извлечем документ определения службы а также доступ к ресурсам службы данных, отправляя запросы HTTP GET через веб-браузер к предоставляемым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-104">You will then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4b4b-105">По умолчанию Visual Studio автоматически приписывает для URI на компьютере номер порта `localhost`.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-105">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="d4b4b-106">В данной задаче в примерах URI используется порт номер `12345`.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-106">This task uses the port number `12345` in the URI examples.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d4b4b-107"> как задать конкретный номер порта, см. в разделе проекта в Visual Studio [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="d4b4b-107"> how to set a specific port number in your Visual Studio project see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
### <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="d4b4b-108">Запрос сервисного документа по умолчанию с помощью Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="d4b4b-108">To request the default service document by using Internet Explorer</span></span>  
  
1.  <span data-ttu-id="d4b4b-109">В Internet Explorer из **средства** последовательно выберите пункты **обозревателя**, нажмите кнопку **содержимого** щелкните **параметры**и снимите  **Включение просмотра веб-канала**.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-109">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>  
  
     <span data-ttu-id="d4b4b-110">При этом чтение каналов будет отключено.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-110">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="d4b4b-111">Если не выключить эту функцию, то веб-браузер будет рассматривать документ в формате AtomPub в качестве канала XML, а не отображать необработанные данные XML.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-111">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4b4b-112">Если браузер не может отобразить канал в виде необработанных XML-данных, его все равно можно просмотреть в виде исходного кода страницы.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-112">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>  
  
2.  <span data-ttu-id="d4b4b-113">Нажмите в Visual Studio клавишу F5 для запуска отладки приложения.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-113">In Visual Studio, press the F5 key to start debugging the application.</span></span>  
  
3.  <span data-ttu-id="d4b4b-114">Откройте веб-браузер на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-114">Open a Web browser on the local computer.</span></span> <span data-ttu-id="d4b4b-115">В адресной строке введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-115">In the address bar, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     <span data-ttu-id="d4b4b-116">При этом будет возвращен сервисный документ по умолчанию, в котором содержится список наборов сущностей, предоставляемых службой данных.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-116">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>  
  
### <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="d4b4b-117">Доступ к ресурсам набора сущностей из веб-браузера</span><span class="sxs-lookup"><span data-stu-id="d4b4b-117">To access entity set resources from a Web browser</span></span>  
  
1.  <span data-ttu-id="d4b4b-118">В адресной строке веб-браузера введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-118">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     <span data-ttu-id="d4b4b-119">При этом будет возвращен набор всех клиентов из образца базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-119">This returns a set of all customers in the Northwind sample database.</span></span>  
  
2.  <span data-ttu-id="d4b4b-120">В адресной строке веб-браузера введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-120">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     <span data-ttu-id="d4b4b-121">При этом возвращается экземпляр сущности для конкретного клиента `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-121">This returns an entity instance for the specific customer, `ALFKI`.</span></span>  
  
3.  <span data-ttu-id="d4b4b-122">В адресной строке веб-браузера введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-122">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     <span data-ttu-id="d4b4b-123">При этом произойдет переход по связи между клиентами и заказами для возвращения набора всех заказов для конкретного клиента `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-123">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>  
  
4.  <span data-ttu-id="d4b4b-124">В адресной строке веб-браузера введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-124">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     <span data-ttu-id="d4b4b-125">При этом будут отфильтрованы заказы, принадлежащие конкретному клиенту `ALFKI`, в результате чего будет возвращен только конкретный заказ на основе переданного значения `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-125">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d4b4b-126">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="d4b4b-126">Next Steps</span></span>  
 <span data-ttu-id="d4b4b-127">Итак, мы успешно обратились к службам [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] из веб-браузера, отправляя через браузер запросы HTTP GET к указанным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-127">You have successfully accessed the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="d4b4b-128">Веб-браузер предоставляет простой способ проведения экспериментов с синтаксисом адресации запросов и просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-128">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="d4b4b-129">Однако к производственной службе данных таким способом обычно не обращаются.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-129">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="d4b4b-130">Как правило, взаимодействие приложений со службой данных осуществляется через программный код или языки сценариев.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-130">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="d4b4b-131">Далее мы создадим клиентское приложение, которое использует клиентские библиотеки для обращения к ресурсам службы данных, как если бы они являлись объектами CLR.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-131">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>  
  
 [<span data-ttu-id="d4b4b-132">Создание клиентского приложения .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4b4b-132">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="d4b4b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d4b4b-133">See Also</span></span>  
 [<span data-ttu-id="d4b4b-134">Доступ к ресурсам служб данных</span><span class="sxs-lookup"><span data-stu-id="d4b4b-134">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
