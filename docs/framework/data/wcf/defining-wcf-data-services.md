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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 888f0af14e31c432cd4ad737232a22ed6f079a3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="ca829-102">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="ca829-102">Defining WCF Data Services</span></span>
<span data-ttu-id="ca829-103">В этом разделе описывается создание и настройка [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для предоставления данных в виде [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала.</span><span class="sxs-lookup"><span data-stu-id="ca829-103">This section describes how to create and configure [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ca829-104">Основные шаги, необходимые для создания службы данных, в разделе [предоставление данных как служба](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ca829-104"> the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca829-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="ca829-105">In This Section</span></span>  
 [<span data-ttu-id="ca829-106">Настройка службы данных</span><span class="sxs-lookup"><span data-stu-id="ca829-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="ca829-107">Описывает параметры конфигурации службы данных, предоставляемые [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca829-107">Describes the data service configuration options provided by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="ca829-108">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="ca829-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 <span data-ttu-id="ca829-109">Описывает модели поставщиков для предоставления данных в виде службы данных.</span><span class="sxs-lookup"><span data-stu-id="ca829-109">Describes the provider models for exposing data as a data service.</span></span>  
  
 [<span data-ttu-id="ca829-110">Операции службы</span><span class="sxs-lookup"><span data-stu-id="ca829-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)  
 <span data-ttu-id="ca829-111">Описывает определение операций службы, которые предоставляют доступ к методам на сервере.</span><span class="sxs-lookup"><span data-stu-id="ca829-111">Describes how to define service operations that expose methods on the server.</span></span>  
  
 [<span data-ttu-id="ca829-112">Настройка каналов</span><span class="sxs-lookup"><span data-stu-id="ca829-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)  
 <span data-ttu-id="ca829-113">Описывает создание сопоставлений между сущностями модели данных, определенной поставщиком службы данных, и элементами канала данных.</span><span class="sxs-lookup"><span data-stu-id="ca829-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>  
  
 [<span data-ttu-id="ca829-114">Перехватчики</span><span class="sxs-lookup"><span data-stu-id="ca829-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)  
 <span data-ttu-id="ca829-115">Описывает определение методов перехватчиков для применения к запросам к службе данных пользовательской бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="ca829-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>  
  
 [<span data-ttu-id="ca829-116">Разработка и развертывание служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="ca829-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)  
 <span data-ttu-id="ca829-117">Описывает разработку и развертывание службы данных с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ca829-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>  
  
 [<span data-ttu-id="ca829-118">Защита служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="ca829-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 <span data-ttu-id="ca829-119">Содержит описание проверки подлинности и авторизации для службы данных и другие рекомендации по безопасности.</span><span class="sxs-lookup"><span data-stu-id="ca829-119">Describes authentication and authorization for the data service and other security considerations.</span></span>  
  
 [<span data-ttu-id="ca829-120">Размещение служб данных</span><span class="sxs-lookup"><span data-stu-id="ca829-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="ca829-121">Описывает метод выбора размещения для службы данных.</span><span class="sxs-lookup"><span data-stu-id="ca829-121">Describes how to select a host for your data service.</span></span>  
  
 [<span data-ttu-id="ca829-122">Управление версиями службы данных</span><span class="sxs-lookup"><span data-stu-id="ca829-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)  
 <span data-ttu-id="ca829-123">Описывает работу с разными версиями [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca829-123">Describes how to work with different versions of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span>  
  
 [<span data-ttu-id="ca829-124">Сведения о реализации протокола служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="ca829-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)  
 <span data-ttu-id="ca829-125">Описывает дополнительные функции протокола [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], которые в настоящее время не реализованы в службах WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="ca829-125">Describes optional functionalities of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol that are not currently implemented by WCF Data Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca829-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ca829-126">See Also</span></span>  
 [<span data-ttu-id="ca829-127">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="ca829-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="ca829-128">Доступ к ресурсам службы данных</span><span class="sxs-lookup"><span data-stu-id="ca829-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)  
 [<span data-ttu-id="ca829-129">Начало работы</span><span class="sxs-lookup"><span data-stu-id="ca829-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
