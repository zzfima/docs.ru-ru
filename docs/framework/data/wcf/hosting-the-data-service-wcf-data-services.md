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
ms.openlocfilehash: 3abcd901bcb8a175aa6f30e53b142cbbde56a579
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975246"
---
# <a name="hosting-the-data-service-wcf-data-services"></a><span data-ttu-id="350dd-102">Размещение служб данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="350dd-102">Hosting the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="350dd-103">С помощью WCF Data Services можно создать службу, которая предоставляет данные в виде веб-канала Open Data Protocol (OData).</span><span class="sxs-lookup"><span data-stu-id="350dd-103">By using WCF Data Services, you can create a service that exposes data as an Open Data Protocol (OData) feed.</span></span> <span data-ttu-id="350dd-104">Эта служба данных определена в качестве класса, наследуемого от <xref:System.Data.Services.DataService%601>.</span><span class="sxs-lookup"><span data-stu-id="350dd-104">This data service is defined as a class that inherits from <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="350dd-105">Этот класс предоставляет функции, необходимые для обработки сообщений запросов, выполнения обновлений для источника данных и создания сообщений ответов в соответствии с требованиями OData.</span><span class="sxs-lookup"><span data-stu-id="350dd-105">This class provides the functionality required to process request messages, perform updates against the data source, and generate responses messages, as required by OData.</span></span> <span data-ttu-id="350dd-106">Однако службе данных не удается выполнить привязку и прослушивание сетевого сокета для входящих HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="350dd-106">However, a data service cannot bind to and listen on a network socket for incoming HTTP requests.</span></span> <span data-ttu-id="350dd-107">Реализацию этой обязательной функциональности служба данных возлагает на размещающий компонент.</span><span class="sxs-lookup"><span data-stu-id="350dd-107">For this required functionality, the data service relies on a hosting component.</span></span>

 <span data-ttu-id="350dd-108">Узел службы данных выполняет следующие задачи от имени источника данных:</span><span class="sxs-lookup"><span data-stu-id="350dd-108">The data service host performs the following tasks on behalf of the data service:</span></span>

- <span data-ttu-id="350dd-109">Прослушивает запросы и перенаправляет их службе данных.</span><span class="sxs-lookup"><span data-stu-id="350dd-109">Listens for requests and routes these requests to the data service.</span></span>

- <span data-ttu-id="350dd-110">Создает экземпляр службы данных для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="350dd-110">Creates an instance of the data service for each request.</span></span>

- <span data-ttu-id="350dd-111">Запрашивает обработку входящего запроса службой данных.</span><span class="sxs-lookup"><span data-stu-id="350dd-111">Requests that the data service process the incoming request.</span></span>

- <span data-ttu-id="350dd-112">Отправляет ответ от имени службы данных.</span><span class="sxs-lookup"><span data-stu-id="350dd-112">Sends the response on behalf of the data service.</span></span>

 <span data-ttu-id="350dd-113">Для упрощения размещения службы данных WCF Data Services предназначен для интеграции с Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="350dd-113">To simplify hosting a data service, WCF Data Services is designed to integrate with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="350dd-114">Служба данных предоставляет реализацию WCF по умолчанию, которая служит узлом службы данных в приложении ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="350dd-114">The data service provides a default WCF implementation that serves as the data service host in an ASP.NET application.</span></span> <span data-ttu-id="350dd-115">Следовательно, службу данных можно разместить одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="350dd-115">Therefore, you can host a data service in one of the following ways:</span></span>

- <span data-ttu-id="350dd-116">В приложении ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="350dd-116">In an ASP.NET application.</span></span>

- <span data-ttu-id="350dd-117">В управляемом приложении, которое поддерживает резидентные службы WCF.</span><span class="sxs-lookup"><span data-stu-id="350dd-117">In a managed application that supports self-hosted WCF services.</span></span>

- <span data-ttu-id="350dd-118">В других специализированных узлах службы данных.</span><span class="sxs-lookup"><span data-stu-id="350dd-118">In some other custom data service host.</span></span>

## <a name="hosting-a-data-service-in-an-aspnet-application"></a><span data-ttu-id="350dd-119">Размещение службы данных в приложении ASP.NET</span><span class="sxs-lookup"><span data-stu-id="350dd-119">Hosting a Data Service in an ASP.NET Application</span></span>

<span data-ttu-id="350dd-120">При использовании диалогового окна **Добавление нового элемента** в Visual Studio 2015 для определения службы данных в приложении ASP.NET это средство создает два новых файла в проекте.</span><span class="sxs-lookup"><span data-stu-id="350dd-120">When you use the **Add New Item** dialog in Visual Studio 2015 to define a data service in an ASP.NET application, the tool generates two new files in the project.</span></span> <span data-ttu-id="350dd-121">Первый файл имеет расширение `.svc` и определяет для среды выполнения WCF способ создания экземпляра службы данных.</span><span class="sxs-lookup"><span data-stu-id="350dd-121">The first file has a `.svc` extension and instructs the WCF runtime how to instantiate the data service.</span></span> <span data-ttu-id="350dd-122">Ниже приведен пример этого файла для образца службы данных Northwind, созданного при выполнении [краткого руководства](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="350dd-122">The following is an example of this file for the Northwind sample data service created when you complete the [quickstart](quickstart-wcf-data-services.md):</span></span>

```aspx-csharp
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 <span data-ttu-id="350dd-123">Эта директива используется для инструкции приложения для создания узла службы для именованного класса службы данных путем использования класса <xref:System.Data.Services.DataServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="350dd-123">This directive tells the application to create the service host for the named data service class by using the <xref:System.Data.Services.DataServiceHostFactory> class.</span></span>

 <span data-ttu-id="350dd-124">Страница с выделенным кодом для файла `.svc` содержит класс, являющийся реализацией самой службы данных, определенной следующим образом для образца службы данных Northwind:</span><span class="sxs-lookup"><span data-stu-id="350dd-124">The code-behind page for the `.svc` file contains the class that is the implementation of the data service itself, which is defined as follows for the Northwind sample data service:</span></span>

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

 <span data-ttu-id="350dd-125">Так как служба данных ведет себя как служба WCF, служба данных интегрируется с ASP.NET и соответствует модели веб-программирования WCF.</span><span class="sxs-lookup"><span data-stu-id="350dd-125">Because a data service behaves like a WCF service, the data service integrates with ASP.NET and follows the WCF Web programming model.</span></span> <span data-ttu-id="350dd-126">Дополнительные сведения см. в статьях [службы WCF и ASP.NET](../../wcf/feature-details/wcf-services-and-aspnet.md) и [модель программирования веб-HTTP WCF](../../wcf/feature-details/wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="350dd-126">For more information, see [WCF Services and ASP.NET](../../wcf/feature-details/wcf-services-and-aspnet.md) and [WCF Web HTTP Programming Model](../../wcf/feature-details/wcf-web-http-programming-model.md).</span></span>

## <a name="self-hosted-wcf-services"></a><span data-ttu-id="350dd-127">Резидентные службы WCF</span><span class="sxs-lookup"><span data-stu-id="350dd-127">Self-Hosted WCF Services</span></span>
 <span data-ttu-id="350dd-128">Так как она включает реализацию WCF, WCF Data Services поддерживает самостоятельное размещение службы данных в качестве службы WCF.</span><span class="sxs-lookup"><span data-stu-id="350dd-128">Because it incorporates a WCF implementation, WCF Data Services support self-hosting a data service as a WCF service.</span></span> <span data-ttu-id="350dd-129">Служба может быть размещена самостоятельно в любом приложении .NET Framework, например в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="350dd-129">A service can be self-hosted in any .NET Framework application, such as a console application.</span></span> <span data-ttu-id="350dd-130">Класс <xref:System.Data.Services.DataServiceHost>, наследуемый от <xref:System.ServiceModel.Web.WebServiceHost>, используется для создания экземпляров службы данных по определенному адресу.</span><span class="sxs-lookup"><span data-stu-id="350dd-130">The <xref:System.Data.Services.DataServiceHost> class, which inherits from <xref:System.ServiceModel.Web.WebServiceHost>, is used to instantiate the data service at a specific address.</span></span>

 <span data-ttu-id="350dd-131">Резидентное размещение можно использовать для разработки и тестирования, поскольку оно упрощает развертывание и диагностику службы.</span><span class="sxs-lookup"><span data-stu-id="350dd-131">Self-hosting can be used for development and testing because it can make it easier to deploy and troubleshoot the service.</span></span> <span data-ttu-id="350dd-132">Однако этот тип размещения не предоставляет расширенные функции размещения и управления, предоставляемые ASP.NET или службы IIS (IIS).</span><span class="sxs-lookup"><span data-stu-id="350dd-132">However, this kind of hosting does not provide the advanced hosting and management features provided by ASP.NET or by Internet Information Services (IIS).</span></span> <span data-ttu-id="350dd-133">Дополнительные сведения см. [в разделе Размещение в управляемом приложении](../../wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="350dd-133">For more information, see [Hosting in a Managed Application](../../wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

## <a name="defining-a-custom-data-service-host"></a><span data-ttu-id="350dd-134">Определение специализированных узлов служб данных</span><span class="sxs-lookup"><span data-stu-id="350dd-134">Defining a Custom Data Service Host</span></span>
 <span data-ttu-id="350dd-135">В случае если ограничения, связанные с реализацией узла WCF, неприемлемы, для службы данных можно также определить настраиваемый узел.</span><span class="sxs-lookup"><span data-stu-id="350dd-135">For cases where the WCF host implementation is too restrictive, you can also define a custom host for a data service.</span></span> <span data-ttu-id="350dd-136">Любой класс, реализующий интерфейс <xref:System.Data.Services.IDataServiceHost>, можно использовать в качестве сетевого узла для службы данных.</span><span class="sxs-lookup"><span data-stu-id="350dd-136">Any class that implements <xref:System.Data.Services.IDataServiceHost> interface can be used as the network host for a data service.</span></span> <span data-ttu-id="350dd-137">Настраиваемый узел должен реализовать интерфейс <xref:System.Data.Services.IDataServiceHost> и поддерживать следующие основные функции узла службы данных:</span><span class="sxs-lookup"><span data-stu-id="350dd-137">A custom host must implement the <xref:System.Data.Services.IDataServiceHost> interface and be able to handle the following basic responsibilities of the data service host:</span></span>

- <span data-ttu-id="350dd-138">Обеспечивать службу данных корневым путем службы.</span><span class="sxs-lookup"><span data-stu-id="350dd-138">Provide the data service with the service root path.</span></span>

- <span data-ttu-id="350dd-139">Обрабатывать данные заголовков запроса и ответа в соответствующей реализации элемента <xref:System.Data.Services.IDataServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="350dd-139">Process request and response headers information to the appropriate <xref:System.Data.Services.IDataServiceHost> member implementation.</span></span>

- <span data-ttu-id="350dd-140">Обрабатывать исключения, сформированные службой данных.</span><span class="sxs-lookup"><span data-stu-id="350dd-140">Handle exceptions raised by the data service.</span></span>

- <span data-ttu-id="350dd-141">Проверять параметры в строке запроса.</span><span class="sxs-lookup"><span data-stu-id="350dd-141">Validate parameters in the query string.</span></span>

## <a name="see-also"></a><span data-ttu-id="350dd-142">См. также</span><span class="sxs-lookup"><span data-stu-id="350dd-142">See also</span></span>

- [<span data-ttu-id="350dd-143">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="350dd-143">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="350dd-144">Предоставление данных как службы</span><span class="sxs-lookup"><span data-stu-id="350dd-144">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
- [<span data-ttu-id="350dd-145">Настройка службы данных</span><span class="sxs-lookup"><span data-stu-id="350dd-145">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)
