---
title: Определение служб данных WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: c0c9010a71877d2c9757a2c9cf2d5c1fec8aedf7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515541"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="cff32-102">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="cff32-102">Defining WCF Data Services</span></span>

<span data-ttu-id="cff32-103">В этом разделе описывается создание и настройка служб данных WCF для предоставления данных в виде [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала.</span><span class="sxs-lookup"><span data-stu-id="cff32-103">This section describes how to create and configure WCF Data Services to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="cff32-104">Дополнительные сведения о основные шаги, необходимые для создания службы данных, см. в разделе [предоставление данных как услуга](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cff32-104">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cff32-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="cff32-105">In This Section</span></span>

 [<span data-ttu-id="cff32-106">Настройка службы данных</span><span class="sxs-lookup"><span data-stu-id="cff32-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="cff32-107">Описывает параметры конфигурации службы данных, предоставляемые службами WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="cff32-107">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="cff32-108">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="cff32-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)

 <span data-ttu-id="cff32-109">Описывает модели поставщиков для предоставления данных в виде службы данных.</span><span class="sxs-lookup"><span data-stu-id="cff32-109">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="cff32-110">Операции служб</span><span class="sxs-lookup"><span data-stu-id="cff32-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)

 <span data-ttu-id="cff32-111">Описывает определение операций службы, которые предоставляют доступ к методам на сервере.</span><span class="sxs-lookup"><span data-stu-id="cff32-111">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="cff32-112">Настройка каналов</span><span class="sxs-lookup"><span data-stu-id="cff32-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)

 <span data-ttu-id="cff32-113">Описывает создание сопоставлений между сущностями модели данных, определенной поставщиком службы данных, и элементами канала данных.</span><span class="sxs-lookup"><span data-stu-id="cff32-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="cff32-114">Перехватчики</span><span class="sxs-lookup"><span data-stu-id="cff32-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)

 <span data-ttu-id="cff32-115">Описывает определение методов перехватчиков для применения к запросам к службе данных пользовательской бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="cff32-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="cff32-116">Разработка и развертывание служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cff32-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="cff32-117">Описывает разработку и развертывание службы данных с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cff32-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="cff32-118">Защита служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cff32-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)

 <span data-ttu-id="cff32-119">Содержит описание проверки подлинности и авторизации для службы данных и другие рекомендации по безопасности.</span><span class="sxs-lookup"><span data-stu-id="cff32-119">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="cff32-120">Размещение служб данных</span><span class="sxs-lookup"><span data-stu-id="cff32-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="cff32-121">Описывает метод выбора размещения для службы данных.</span><span class="sxs-lookup"><span data-stu-id="cff32-121">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="cff32-122">Управление версиями служб данных</span><span class="sxs-lookup"><span data-stu-id="cff32-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="cff32-123">В этой статье описывается работа с разными версиями OData.</span><span class="sxs-lookup"><span data-stu-id="cff32-123">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="cff32-124">Сведения о реализации протокола служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cff32-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="cff32-125">Описывает дополнительные функции протокола OData, которые в настоящее время не реализованы в службах WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="cff32-125">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="cff32-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cff32-126">See Also</span></span>

- [<span data-ttu-id="cff32-127">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="cff32-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [<span data-ttu-id="cff32-128">Доступ к ресурсам служб данных</span><span class="sxs-lookup"><span data-stu-id="cff32-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="cff32-129">Начало работы</span><span class="sxs-lookup"><span data-stu-id="cff32-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
