---
title: Размещение служб данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: e738fa1feebdd91bdb84484340b31e599d7f5f76
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765577"
---
# <a name="hosting-the-data-service-wcf-data-services"></a><span data-ttu-id="9a17b-102">Размещение служб данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="9a17b-102">Hosting the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="9a17b-103">С помощью служб данных WCF, можно создать службу, предоставляющую данные в виде [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала.</span><span class="sxs-lookup"><span data-stu-id="9a17b-103">By using WCF Data Services, you can create a service that exposes data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="9a17b-104">Эта служба данных определена в качестве класса, наследуемого от <xref:System.Data.Services.DataService%601>.</span><span class="sxs-lookup"><span data-stu-id="9a17b-104">This data service is defined as a class that inherits from <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="9a17b-105">Этот класс предоставляет функциональность, необходимую для обработки сообщения запроса, выполнения обновлений в источнике данных и создания ответных сообщений, требует OData.</span><span class="sxs-lookup"><span data-stu-id="9a17b-105">This class provides the functionality required to process request messages, perform updates against the data source, and generate responses messages, as required by OData.</span></span> <span data-ttu-id="9a17b-106">Тем не менее службы данных невозможно привязать к и прослушивать входящие запросы HTTP к сетевому сокету.</span><span class="sxs-lookup"><span data-stu-id="9a17b-106">However, a data service cannot bind to and listen on a network socket for incoming HTTP requests.</span></span> <span data-ttu-id="9a17b-107">Реализацию этой обязательной функциональности служба данных возлагает на размещающий компонент.</span><span class="sxs-lookup"><span data-stu-id="9a17b-107">For this required functionality, the data service relies on a hosting component.</span></span>

 <span data-ttu-id="9a17b-108">Узел службы данных выполняет следующие задачи от имени источника данных:</span><span class="sxs-lookup"><span data-stu-id="9a17b-108">The data service host performs the following tasks on behalf of the data service:</span></span>

- <span data-ttu-id="9a17b-109">Прослушивает запросы и перенаправляет их службе данных.</span><span class="sxs-lookup"><span data-stu-id="9a17b-109">Listens for requests and routes these requests to the data service.</span></span>

- <span data-ttu-id="9a17b-110">Создает экземпляр службы данных для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="9a17b-110">Creates an instance of the data service for each request.</span></span>

- <span data-ttu-id="9a17b-111">Запрашивает обработку входящего запроса службой данных.</span><span class="sxs-lookup"><span data-stu-id="9a17b-111">Requests that the data service process the incoming request.</span></span>

- <span data-ttu-id="9a17b-112">Отправляет ответ от имени службы данных.</span><span class="sxs-lookup"><span data-stu-id="9a17b-112">Sends the response on behalf of the data service.</span></span>

 <span data-ttu-id="9a17b-113">Чтобы упростить размещение службы данных, службы данных WCF предназначен для интеграции с Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9a17b-113">To simplify hosting a data service, WCF Data Services is designed to integrate with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="9a17b-114">Эта служба данных предоставляет реализацию по умолчанию WCF, который служит в качестве узла службы данных в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="9a17b-114">The data service provides a default WCF implementation that serves as the data service host in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="9a17b-115">Следовательно, службу данных можно разместить одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="9a17b-115">Therefore, you can host a data service in one of the following ways:</span></span>

- <span data-ttu-id="9a17b-116">В приложении [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a17b-116">In an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>

- <span data-ttu-id="9a17b-117">В управляемом приложении, которое поддерживает резидентные службы WCF.</span><span class="sxs-lookup"><span data-stu-id="9a17b-117">In a managed application that supports self-hosted WCF services.</span></span>

- <span data-ttu-id="9a17b-118">В других специализированных узлах службы данных.</span><span class="sxs-lookup"><span data-stu-id="9a17b-118">In some other custom data service host.</span></span>

## <a name="hosting-a-data-service-in-an-aspnet-application"></a><span data-ttu-id="9a17b-119">Размещение службы данных в приложении ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9a17b-119">Hosting a Data Service in an ASP.NET Application</span></span>

<span data-ttu-id="9a17b-120">При использовании **Добавление нового элемента** диалоговое окно в Visual Studio 2015 для определения службы данных в приложении ASP.NET, средство создает два новых файла в проекте.</span><span class="sxs-lookup"><span data-stu-id="9a17b-120">When you use the **Add New Item** dialog in Visual Studio 2015 to define a data service in an ASP.NET application, the tool generates two new files in the project.</span></span> <span data-ttu-id="9a17b-121">Первый файл имеет расширение `.svc` и определяет для среды выполнения WCF способ создания экземпляра службы данных.</span><span class="sxs-lookup"><span data-stu-id="9a17b-121">The first file has a `.svc` extension and instructs the WCF runtime how to instantiate the data service.</span></span> <span data-ttu-id="9a17b-122">Ниже приведен пример этого файла для образца службы данных Northwind создана при выполнении [быстрого запуска](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):</span><span class="sxs-lookup"><span data-stu-id="9a17b-122">The following is an example of this file for the Northwind sample data service created when you complete the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):</span></span>

```
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 <span data-ttu-id="9a17b-123">Эта директива используется для инструкции приложения для создания узла службы для именованного класса службы данных путем использования класса <xref:System.Data.Services.DataServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="9a17b-123">This directive tells the application to create the service host for the named data service class by using the <xref:System.Data.Services.DataServiceHostFactory> class.</span></span>

 <span data-ttu-id="9a17b-124">Страница с выделенным кодом для файла `.svc` содержит класс, являющийся реализацией самой службы данных, определенной следующим образом для образца службы данных Northwind:</span><span class="sxs-lookup"><span data-stu-id="9a17b-124">The code-behind page for the `.svc` file contains the class that is the implementation of the data service itself, which is defined as follows for the Northwind sample data service:</span></span>

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

 <span data-ttu-id="9a17b-125">Поскольку служба данных работает аналогично службе WCF, она интегрируется с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и соответствует модели веб-программирования WCF.</span><span class="sxs-lookup"><span data-stu-id="9a17b-125">Because a data service behaves like a WCF service, the data service integrates with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] and follows the WCF Web programming model.</span></span> <span data-ttu-id="9a17b-126">Дополнительные сведения см. в разделе [службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) и [модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="9a17b-126">For more information, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) and [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span></span>

## <a name="self-hosted-wcf-services"></a><span data-ttu-id="9a17b-127">Резидентные службы WCF</span><span class="sxs-lookup"><span data-stu-id="9a17b-127">Self-Hosted WCF Services</span></span>
 <span data-ttu-id="9a17b-128">Так как он включает в себя реализацию WCF, WCF Data Services поддерживают размещения службы данных в качестве службы WCF на собственном сервере.</span><span class="sxs-lookup"><span data-stu-id="9a17b-128">Because it incorporates a WCF implementation, WCF Data Services support self-hosting a data service as a WCF service.</span></span> <span data-ttu-id="9a17b-129">Служба может быть резидентно размещена в любом приложении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], например в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="9a17b-129">A service can be self-hosted in any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application, such as a console application.</span></span> <span data-ttu-id="9a17b-130">Класс <xref:System.Data.Services.DataServiceHost>, наследуемый от <xref:System.ServiceModel.Web.WebServiceHost>, используется для создания экземпляров службы данных по определенному адресу.</span><span class="sxs-lookup"><span data-stu-id="9a17b-130">The <xref:System.Data.Services.DataServiceHost> class, which inherits from <xref:System.ServiceModel.Web.WebServiceHost>, is used to instantiate the data service at a specific address.</span></span>

 <span data-ttu-id="9a17b-131">Резидентное размещение можно использовать для разработки и тестирования, поскольку оно упрощает развертывание и диагностику службы.</span><span class="sxs-lookup"><span data-stu-id="9a17b-131">Self-hosting can be used for development and testing because it can make it easier to deploy and troubleshoot the service.</span></span> <span data-ttu-id="9a17b-132">Однако этот тип размещения не обеспечивает дополнительные функции размещения и управления, обеспечиваемые [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] или службами IIS.</span><span class="sxs-lookup"><span data-stu-id="9a17b-132">However, this kind of hosting does not provide the advanced hosting and management features provided by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] or by Internet Information Services (IIS).</span></span> <span data-ttu-id="9a17b-133">Дополнительные сведения см. в разделе [размещение в приложении управляемых](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="9a17b-133">For more information, see [Hosting in a Managed Application](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

## <a name="defining-a-custom-data-service-host"></a><span data-ttu-id="9a17b-134">Определение специализированных узлов служб данных</span><span class="sxs-lookup"><span data-stu-id="9a17b-134">Defining a Custom Data Service Host</span></span>
 <span data-ttu-id="9a17b-135">В случае если ограничения, связанные с реализацией узла WCF, неприемлемы, для службы данных можно также определить настраиваемый узел.</span><span class="sxs-lookup"><span data-stu-id="9a17b-135">For cases where the WCF host implementation is too restrictive, you can also define a custom host for a data service.</span></span> <span data-ttu-id="9a17b-136">Любой класс, реализующий интерфейс <xref:System.Data.Services.IDataServiceHost>, можно использовать в качестве сетевого узла для службы данных.</span><span class="sxs-lookup"><span data-stu-id="9a17b-136">Any class that implements <xref:System.Data.Services.IDataServiceHost> interface can be used as the network host for a data service.</span></span> <span data-ttu-id="9a17b-137">Настраиваемый узел должен реализовать интерфейс <xref:System.Data.Services.IDataServiceHost> и поддерживать следующие основные функции узла службы данных:</span><span class="sxs-lookup"><span data-stu-id="9a17b-137">A custom host must implement the <xref:System.Data.Services.IDataServiceHost> interface and be able to handle the following basic responsibilities of the data service host:</span></span>

- <span data-ttu-id="9a17b-138">Обеспечивать службу данных корневым путем службы.</span><span class="sxs-lookup"><span data-stu-id="9a17b-138">Provide the data service with the service root path.</span></span>

- <span data-ttu-id="9a17b-139">Обрабатывать данные заголовков запроса и ответа в соответствующей реализации элемента <xref:System.Data.Services.IDataServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="9a17b-139">Process request and response headers information to the appropriate <xref:System.Data.Services.IDataServiceHost> member implementation.</span></span>

- <span data-ttu-id="9a17b-140">Обрабатывать исключения, сформированные службой данных.</span><span class="sxs-lookup"><span data-stu-id="9a17b-140">Handle exceptions raised by the data service.</span></span>

- <span data-ttu-id="9a17b-141">Проверять параметры в строке запроса.</span><span class="sxs-lookup"><span data-stu-id="9a17b-141">Validate parameters in the query string.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a17b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="9a17b-142">See also</span></span>

- [<span data-ttu-id="9a17b-143">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="9a17b-143">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [<span data-ttu-id="9a17b-144">Предоставление данных как службы</span><span class="sxs-lookup"><span data-stu-id="9a17b-144">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
- [<span data-ttu-id="9a17b-145">Настройка службы данных</span><span class="sxs-lookup"><span data-stu-id="9a17b-145">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
