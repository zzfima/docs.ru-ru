---
title: Определение служб данных WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: b9280936a16d50283c01120c9dc046e65a0a79ae
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790871"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="381e8-102">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="381e8-102">Defining WCF Data Services</span></span>

<span data-ttu-id="381e8-103">В этом разделе описывается создание и Настройка WCF Data Services для предоставления данных в виде [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала.</span><span class="sxs-lookup"><span data-stu-id="381e8-103">This section describes how to create and configure WCF Data Services to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="381e8-104">Дополнительные сведения о базовых шагах, необходимых для создания службы данных, см. в разделе [предоставление данных в виде службы](exposing-your-data-as-a-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="381e8-104">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="381e8-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="381e8-105">In This Section</span></span>

 [<span data-ttu-id="381e8-106">Настройка службы данных</span><span class="sxs-lookup"><span data-stu-id="381e8-106">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="381e8-107">Описывает параметры конфигурации службы данных, предоставляемые WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="381e8-107">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="381e8-108">Поставщики служб данных</span><span class="sxs-lookup"><span data-stu-id="381e8-108">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)

 <span data-ttu-id="381e8-109">Описывает модели поставщиков для предоставления данных в виде службы данных.</span><span class="sxs-lookup"><span data-stu-id="381e8-109">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="381e8-110">Операции служб</span><span class="sxs-lookup"><span data-stu-id="381e8-110">Service Operations</span></span>](service-operations-wcf-data-services.md)

 <span data-ttu-id="381e8-111">Описывает определение операций службы, которые предоставляют доступ к методам на сервере.</span><span class="sxs-lookup"><span data-stu-id="381e8-111">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="381e8-112">Настройка каналов</span><span class="sxs-lookup"><span data-stu-id="381e8-112">Feed Customization</span></span>](feed-customization-wcf-data-services.md)

 <span data-ttu-id="381e8-113">Описывает создание сопоставлений между сущностями модели данных, определенной поставщиком службы данных, и элементами канала данных.</span><span class="sxs-lookup"><span data-stu-id="381e8-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="381e8-114">Перехватчики</span><span class="sxs-lookup"><span data-stu-id="381e8-114">Interceptors</span></span>](interceptors-wcf-data-services.md)

 <span data-ttu-id="381e8-115">Описывает определение методов перехватчиков для применения к запросам к службе данных пользовательской бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="381e8-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="381e8-116">Разработка и развертывание служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="381e8-116">Developing and Deploying WCF Data Services</span></span>](developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="381e8-117">Описывает разработку и развертывание службы данных с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="381e8-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="381e8-118">Защита служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="381e8-118">Securing WCF Data Services</span></span>](securing-wcf-data-services.md)

 <span data-ttu-id="381e8-119">Содержит описание проверки подлинности и авторизации для службы данных и другие рекомендации по безопасности.</span><span class="sxs-lookup"><span data-stu-id="381e8-119">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="381e8-120">Размещение служб данных</span><span class="sxs-lookup"><span data-stu-id="381e8-120">Hosting the Data Service</span></span>](hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="381e8-121">Описывает метод выбора размещения для службы данных.</span><span class="sxs-lookup"><span data-stu-id="381e8-121">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="381e8-122">Управление версиями служб данных</span><span class="sxs-lookup"><span data-stu-id="381e8-122">Data Service Versioning</span></span>](data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="381e8-123">Описывает работу с различными версиями OData.</span><span class="sxs-lookup"><span data-stu-id="381e8-123">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="381e8-124">Сведения о реализации протокола служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="381e8-124">WCF Data Services Protocol Implementation Details</span></span>](wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="381e8-125">Описывает необязательные функции протокола OData, которые в настоящее время не реализованы WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="381e8-125">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="381e8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="381e8-126">See also</span></span>

- [<span data-ttu-id="381e8-127">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="381e8-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="381e8-128">Доступ к ресурсам служб данных</span><span class="sxs-lookup"><span data-stu-id="381e8-128">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="381e8-129">Начало работы</span><span class="sxs-lookup"><span data-stu-id="381e8-129">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
