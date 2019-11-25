---
title: Краткое руководство (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: d0002182c5ae519c36348acdd2587bca499fe72e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975138"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="30b80-102">Краткое руководство (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="30b80-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="30b80-103">Это краткое руководство поможет вам ознакомиться с WCF Data Services и Open Data Protocol (OData) с помощью серии задач, которые поддерживают разделы в [Начало работы](getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="30b80-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="30b80-104">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="30b80-104">What you'll learn</span></span>

<span data-ttu-id="30b80-105">В первой задаче этого краткого руководства показано, как создать службу данных для предоставления веб-канала OData из образца базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="30b80-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="30b80-106">В последующих разделах вы получите доступ к каналу OData с помощью веб-браузера, а также создаете клиентское приложение Windows Presentation Foundation (WPF), которое использует канал OData с помощью клиентских библиотек.</span><span class="sxs-lookup"><span data-stu-id="30b80-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30b80-107">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="30b80-107">Prerequisites</span></span>

<span data-ttu-id="30b80-108">Чтобы выполнить задания данного краткого руководства, установите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="30b80-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="30b80-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="30b80-109">Visual Studio</span></span>

- <span data-ttu-id="30b80-110">Экземпляр SQL Server.</span><span class="sxs-lookup"><span data-stu-id="30b80-110">An instance of SQL Server.</span></span> <span data-ttu-id="30b80-111">К ним относятся SQL Server Express, которые включены в установку Visual Studio 2015 по умолчанию или как часть рабочей нагрузки **хранения и обработки данных** в visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="30b80-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="30b80-112">Наличие учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="30b80-112">The Northwind sample database.</span></span> <span data-ttu-id="30b80-113">Чтобы скачать этот образец базы данных, см. страницу скачивания [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758)(Образцы баз данных для SQL Server).</span><span class="sxs-lookup"><span data-stu-id="30b80-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="30b80-114">Краткие задачи служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="30b80-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="30b80-115">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="30b80-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="30b80-116">Определите приложение ASP.NET, определите модель данных, создайте службу данных и включите доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="30b80-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="30b80-117">Доступ к службе из веб-браузера</span><span class="sxs-lookup"><span data-stu-id="30b80-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="30b80-118">Запустите службу из среды Visual Studio и обратитесь к ней с помощью запросов HTTP GET через веб-браузер для получения доступа к предоставляемым каналам.</span><span class="sxs-lookup"><span data-stu-id="30b80-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="30b80-119">Создание клиентского приложения .NET Framework</span><span class="sxs-lookup"><span data-stu-id="30b80-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="30b80-120">Создание приложения WPF для использования веб-канала OData, привязки данных к элементам управления Windows, изменения данных в связанных элементах управления и последующей отправки изменений обратно в службу данных.</span><span class="sxs-lookup"><span data-stu-id="30b80-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="30b80-121">Файлы проекта, создаваемого при изучении краткого руководства, можно скачать на странице [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) (Образцы из документации по службам данных WCF).</span><span class="sxs-lookup"><span data-stu-id="30b80-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="30b80-122">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="30b80-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="30b80-123">Запуск краткого руководства</span><span class="sxs-lookup"><span data-stu-id="30b80-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="30b80-124">См. также</span><span class="sxs-lookup"><span data-stu-id="30b80-124">See also</span></span>

- [<span data-ttu-id="30b80-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="30b80-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
