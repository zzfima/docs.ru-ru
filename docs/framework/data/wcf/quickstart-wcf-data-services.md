---
title: Краткое руководство (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f20ffcf356aa0493b1e2356746d9ad7b27d9a1aa
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43330871"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="acfc7-102">Краткое руководство (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="acfc7-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="acfc7-103">Это краткое руководство позволяет ознакомиться со службами данных WCF и [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] через ряд задач, дополняющих содержимое разделов в [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="acfc7-103">This quickstart helps you become familiar with WCF Data Services and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="acfc7-104">Вы узнаете, как</span><span class="sxs-lookup"><span data-stu-id="acfc7-104">What you'll learn</span></span>

<span data-ttu-id="acfc7-105">Первая задача в этом кратком руководстве показано, как создать службу данных для предоставления каналов OData из образца базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="acfc7-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="acfc7-106">В последующих разделах вы будете обращаться к OData веб-канала с помощью веб-браузер, а также создавать Windows Presentation Foundation (WPF) клиентское приложение, использующее OData веб-канала с помощью клиентских библиотек.</span><span class="sxs-lookup"><span data-stu-id="acfc7-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="acfc7-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="acfc7-107">Prerequisites</span></span>

<span data-ttu-id="acfc7-108">Чтобы выполнить задания данного краткого руководства, установите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="acfc7-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="acfc7-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="acfc7-109">Visual Studio</span></span>

- <span data-ttu-id="acfc7-110">Экземпляр SQL Server.</span><span class="sxs-lookup"><span data-stu-id="acfc7-110">An instance of SQL Server.</span></span> <span data-ttu-id="acfc7-111">Это включает SQL Server Express, который включен по умолчанию при установке Visual Studio 2015, или как часть **хранение и обработка данных** рабочей нагрузки в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="acfc7-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="acfc7-112">Наличие учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="acfc7-112">The Northwind sample database.</span></span> <span data-ttu-id="acfc7-113">Чтобы скачать этот образец базы данных, см. на странице загрузки [образцы баз данных для SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="acfc7-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="acfc7-114">Задачи краткого руководства по служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="acfc7-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="acfc7-115">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="acfc7-115">Create the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

 <span data-ttu-id="acfc7-116">Определите приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , определите модель данных, создайте службу данных и включите доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="acfc7-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="acfc7-117">Доступ к службе из веб-браузер</span><span class="sxs-lookup"><span data-stu-id="acfc7-117">Access the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="acfc7-118">Запустите службу из среды Visual Studio и обратитесь к ней с помощью запросов HTTP GET через веб-браузер для получения доступа к предоставляемым каналам.</span><span class="sxs-lookup"><span data-stu-id="acfc7-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="acfc7-119">Создание клиентского приложения .NET Framework</span><span class="sxs-lookup"><span data-stu-id="acfc7-119">Create the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="acfc7-120">Создание приложения WPF для использования канала OData, привязка данных к элементам управления Windows, изменения данных в привязанных элементах управления и отправьте изменения обратно службе данных.</span><span class="sxs-lookup"><span data-stu-id="acfc7-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="acfc7-121">Файлы проекта из полной версии краткого руководства можно загрузить из [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) страницы.</span><span class="sxs-lookup"><span data-stu-id="acfc7-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="acfc7-122">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="acfc7-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="acfc7-123">Начало выполнения краткого руководства</span><span class="sxs-lookup"><span data-stu-id="acfc7-123">Start the quickstart</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="acfc7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="acfc7-124">See also</span></span>

- [<span data-ttu-id="acfc7-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="acfc7-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
