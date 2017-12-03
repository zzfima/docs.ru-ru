---
title: "Определение служб данных WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e66c26c12f3f62ee61e02e16318e747793ff927
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="23d3b-102">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="23d3b-102">Defining WCF Data Services</span></span>
<span data-ttu-id="23d3b-103">В этом разделе описывается создание и настройка [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для предоставления данных в виде [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала.</span><span class="sxs-lookup"><span data-stu-id="23d3b-103">This section describes how to create and configure [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="23d3b-104">Основные шаги, необходимые для создания службы данных, в разделе [предоставление данных как служба](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="23d3b-104"> the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23d3b-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="23d3b-105">In This Section</span></span>  
 [<span data-ttu-id="23d3b-106">Настройка службы данных</span><span class="sxs-lookup"><span data-stu-id="23d3b-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="23d3b-107">Описывает параметры конфигурации службы данных, предоставляемые [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23d3b-107">Describes the data service configuration options provided by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="23d3b-108">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="23d3b-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 <span data-ttu-id="23d3b-109">Описывает модели поставщиков для предоставления данных в виде службы данных.</span><span class="sxs-lookup"><span data-stu-id="23d3b-109">Describes the provider models for exposing data as a data service.</span></span>  
  
 [<span data-ttu-id="23d3b-110">Операции службы</span><span class="sxs-lookup"><span data-stu-id="23d3b-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)  
 <span data-ttu-id="23d3b-111">Описывает определение операций службы, которые предоставляют доступ к методам на сервере.</span><span class="sxs-lookup"><span data-stu-id="23d3b-111">Describes how to define service operations that expose methods on the server.</span></span>  
  
 [<span data-ttu-id="23d3b-112">Настройка каналов</span><span class="sxs-lookup"><span data-stu-id="23d3b-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)  
 <span data-ttu-id="23d3b-113">Описывает создание сопоставлений между сущностями модели данных, определенной поставщиком службы данных, и элементами канала данных.</span><span class="sxs-lookup"><span data-stu-id="23d3b-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>  
  
 [<span data-ttu-id="23d3b-114">Перехватчики</span><span class="sxs-lookup"><span data-stu-id="23d3b-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)  
 <span data-ttu-id="23d3b-115">Описывает определение методов перехватчиков для применения к запросам к службе данных пользовательской бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="23d3b-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>  
  
 [<span data-ttu-id="23d3b-116">Разработка и развертывание служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="23d3b-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)  
 <span data-ttu-id="23d3b-117">Описывает разработку и развертывание службы данных с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="23d3b-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>  
  
 [<span data-ttu-id="23d3b-118">Защита служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="23d3b-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 <span data-ttu-id="23d3b-119">Содержит описание проверки подлинности и авторизации для службы данных и другие рекомендации по безопасности.</span><span class="sxs-lookup"><span data-stu-id="23d3b-119">Describes authentication and authorization for the data service and other security considerations.</span></span>  
  
 [<span data-ttu-id="23d3b-120">Размещение служб данных</span><span class="sxs-lookup"><span data-stu-id="23d3b-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="23d3b-121">Описывает метод выбора размещения для службы данных.</span><span class="sxs-lookup"><span data-stu-id="23d3b-121">Describes how to select a host for your data service.</span></span>  
  
 [<span data-ttu-id="23d3b-122">Управление версиями службы данных</span><span class="sxs-lookup"><span data-stu-id="23d3b-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)  
 <span data-ttu-id="23d3b-123">Описывает работу с разными версиями [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23d3b-123">Describes how to work with different versions of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span>  
  
 [<span data-ttu-id="23d3b-124">Сведения о реализации протокола служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="23d3b-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)  
 <span data-ttu-id="23d3b-125">Описывает дополнительные функции протокола [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], которые в настоящее время не реализованы в службах WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="23d3b-125">Describes optional functionalities of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol that are not currently implemented by WCF Data Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d3b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="23d3b-126">See Also</span></span>  
 [<span data-ttu-id="23d3b-127">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="23d3b-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="23d3b-128">Доступ к ресурсам службы данных</span><span class="sxs-lookup"><span data-stu-id="23d3b-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)  
 [<span data-ttu-id="23d3b-129">Начало работы</span><span class="sxs-lookup"><span data-stu-id="23d3b-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
