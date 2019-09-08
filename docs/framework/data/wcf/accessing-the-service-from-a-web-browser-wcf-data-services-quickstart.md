---
title: Доступ к службе из веб-браузера (краткое руководство по службе данных WCF)
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: eb7f1c97722b45a93c310fb8bcbdb42beece2553
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780540"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="dc73b-102">Доступ к службе из веб-браузера (краткое руководство по службе данных WCF)</span><span class="sxs-lookup"><span data-stu-id="dc73b-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="dc73b-103">Это вторая задача краткого руководства по WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="dc73b-103">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="dc73b-104">В этой задаче вы запускаете WCF Data Services из Visual Studio и при необходимости отключаете чтение веб-канала в браузере.</span><span class="sxs-lookup"><span data-stu-id="dc73b-104">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="dc73b-105">Затем вы получаете документ определения службы и доступ к ресурсам службы данных, отправляя запросы HTTP GET через веб-браузер к предоставленным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="dc73b-105">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="dc73b-106">По умолчанию Visual Studio автоматически приписывает для URI на компьютере номер порта `localhost`.</span><span class="sxs-lookup"><span data-stu-id="dc73b-106">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="dc73b-107">В данной задаче в примерах URI используется порт номер `12345`.</span><span class="sxs-lookup"><span data-stu-id="dc73b-107">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="dc73b-108">Дополнительные сведения о том, как задать конкретный номер порта в проекте Visual Studio, см. в разделе [Создание службы данных](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="dc73b-108">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="dc73b-109">Запрос сервисного документа по умолчанию с помощью Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="dc73b-109">To request the default service document by using Internet Explorer</span></span>

1. <span data-ttu-id="dc73b-110">В Internet Explorer в меню **Сервис** выберите **Свойства обозревателя**, перейдите на вкладку **содержимое** , щелкните **Параметры**и снимите флажок **включить просмотр веб-канала**.</span><span class="sxs-lookup"><span data-stu-id="dc73b-110">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="dc73b-111">При этом чтение каналов будет отключено.</span><span class="sxs-lookup"><span data-stu-id="dc73b-111">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="dc73b-112">Если не выключить эту функцию, то веб-браузер будет рассматривать документ в формате AtomPub в качестве канала XML, а не отображать необработанные данные XML.</span><span class="sxs-lookup"><span data-stu-id="dc73b-112">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc73b-113">Если браузер не может отобразить канал в виде необработанных XML-данных, его все равно можно просмотреть в виде исходного кода страницы.</span><span class="sxs-lookup"><span data-stu-id="dc73b-113">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2. <span data-ttu-id="dc73b-114">В Visual Studio нажмите клавишу **F5** , чтобы начать отладку приложения.</span><span class="sxs-lookup"><span data-stu-id="dc73b-114">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3. <span data-ttu-id="dc73b-115">Откройте веб-браузер на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dc73b-115">Open a Web browser on the local computer.</span></span> <span data-ttu-id="dc73b-116">В адресной строке введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="dc73b-116">In the address bar, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="dc73b-117">При этом будет возвращен сервисный документ по умолчанию, в котором содержится список наборов сущностей, предоставляемых службой данных.</span><span class="sxs-lookup"><span data-stu-id="dc73b-117">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="dc73b-118">Доступ к ресурсам набора сущностей из веб-браузера</span><span class="sxs-lookup"><span data-stu-id="dc73b-118">To access entity set resources from a Web browser</span></span>

1. <span data-ttu-id="dc73b-119">В адресной строке веб-браузера введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="dc73b-119">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="dc73b-120">При этом будет возвращен набор всех клиентов из образца базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="dc73b-120">This returns a set of all customers in the Northwind sample database.</span></span>

2. <span data-ttu-id="dc73b-121">В адресной строке веб-браузера введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="dc73b-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="dc73b-122">При этом возвращается экземпляр сущности для конкретного клиента `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="dc73b-122">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3. <span data-ttu-id="dc73b-123">В адресной строке веб-браузера введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="dc73b-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="dc73b-124">При этом произойдет переход по связи между клиентами и заказами для возвращения набора всех заказов для конкретного клиента `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="dc73b-124">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4. <span data-ttu-id="dc73b-125">В адресной строке веб-браузера введите следующий URI:</span><span class="sxs-lookup"><span data-stu-id="dc73b-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="dc73b-126">При этом будут отфильтрованы заказы, принадлежащие конкретному клиенту `ALFKI`, в результате чего будет возвращен только конкретный заказ на основе переданного значения `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="dc73b-126">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dc73b-127">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="dc73b-127">Next Steps</span></span>

<span data-ttu-id="dc73b-128">Вы успешно получили доступ к WCF Data Services из веб-браузера, где браузер выдает HTTP-запросы GET к указанным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="dc73b-128">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="dc73b-129">Веб-браузер предоставляет простой способ проведения экспериментов с синтаксисом адресации запросов и просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="dc73b-129">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="dc73b-130">Однако к производственной службе данных таким способом обычно не обращаются.</span><span class="sxs-lookup"><span data-stu-id="dc73b-130">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="dc73b-131">Как правило, взаимодействие приложений со службой данных осуществляется через программный код или языки сценариев.</span><span class="sxs-lookup"><span data-stu-id="dc73b-131">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="dc73b-132">Далее мы создадим клиентское приложение, которое использует клиентские библиотеки для обращения к ресурсам службы данных, как если бы они являлись объектами CLR.</span><span class="sxs-lookup"><span data-stu-id="dc73b-132">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dc73b-133">Создание клиентского приложения .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc73b-133">Creating the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="dc73b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="dc73b-134">See also</span></span>

- [<span data-ttu-id="dc73b-135">Доступ к ресурсам служб данных</span><span class="sxs-lookup"><span data-stu-id="dc73b-135">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
