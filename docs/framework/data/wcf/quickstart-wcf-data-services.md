---
title: "Краткое руководство (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a5223f9b6e7854ec6575e8673bb874a1b9b60df7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="ca040-102">Краткое руководство (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="ca040-102">Quickstart (WCF Data Services)</span></span>
<span data-ttu-id="ca040-103">Это краткое руководство поможет вам ознакомиться с [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] и [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] через последовательность задач, которые поддерживают подразделы [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ca040-103">This quickstart helps you become familiar with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="ca040-104">Новые знания</span><span class="sxs-lookup"><span data-stu-id="ca040-104">What You Will Learn</span></span>  
 <span data-ttu-id="ca040-105">Первая задача краткого руководства показывает, как создать службу данных для предоставления канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из образца базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="ca040-105">The first task in this quickstart shows how to create a data service to expose an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from the Northwind sample database.</span></span> <span data-ttu-id="ca040-106">В последующих разделах будет открыт доступ к каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] с помощью веб-браузера и создано клиентское приложение [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] , использующее канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] посредством клиентских библиотек.</span><span class="sxs-lookup"><span data-stu-id="ca040-106">In later topics, you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using a Web browser, and also create a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client application that consumes the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using client libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ca040-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ca040-107">Prerequisites</span></span>  
 <span data-ttu-id="ca040-108">Чтобы выполнить задания данного краткого руководства, установите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="ca040-108">To complete this quickstart, you must install the following components:</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]<span data-ttu-id="ca040-109">.</span><span class="sxs-lookup"><span data-stu-id="ca040-109">.</span></span>  
  
-   <span data-ttu-id="ca040-110">Экземпляр [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca040-110">An instance of [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ca040-111">В том числе SQL Server Express, входящий в установку по умолчанию [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca040-111">This includes SQL Server Express, which is included in a default installation of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="ca040-112">Наличие учебной базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="ca040-112">The Northwind sample database.</span></span> <span data-ttu-id="ca040-113">Чтобы скачать этот образец базы данных, см. страницу скачивания [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758)(Образцы баз данных для SQL Server).</span><span class="sxs-lookup"><span data-stu-id="ca040-113">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="ca040-114">Задачи краткого руководства по службам WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="ca040-114">WCF Data Services Quickstart Tasks</span></span>  
 [<span data-ttu-id="ca040-115">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="ca040-115">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
 <span data-ttu-id="ca040-116">Определите приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , определите модель данных, создайте службу данных и включите доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="ca040-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>  
  
 [<span data-ttu-id="ca040-117">Доступ к службе из веб-браузера</span><span class="sxs-lookup"><span data-stu-id="ca040-117">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
 <span data-ttu-id="ca040-118">Запустите службу из среды [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] и обратитесь к ней с помощью запросов HTTP GET через веб-браузер для получения доступа к предоставляемым каналам.</span><span class="sxs-lookup"><span data-stu-id="ca040-118">Start the service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>  
  
 [<span data-ttu-id="ca040-119">Создание клиентского приложения .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ca040-119">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
 <span data-ttu-id="ca040-120">Создайте клиентское приложение [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] для использования канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] , свяжите данные с элементами управления Windows, измените данные в связанных элементах управления и отправьте изменения обратно в службу данных.</span><span class="sxs-lookup"><span data-stu-id="ca040-120">Create a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] client application to consume the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca040-121">Файлы проекта, создаваемого при изучении краткого руководства, можно скачать на странице [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) (Образцы из документации по службам данных WCF).</span><span class="sxs-lookup"><span data-stu-id="ca040-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ca040-122">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ca040-122">Next Steps</span></span>  
 <span data-ttu-id="ca040-123">[Начало выполнения краткого руководства](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="ca040-123">[Start the Quickstart](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca040-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ca040-124">See Also</span></span>  
 [<span data-ttu-id="ca040-125">Платформа ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ca040-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
