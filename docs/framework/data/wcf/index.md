---
title: Службы WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 148e6e50e81552b2418abba9f6655234fc023c4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365960"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="2e42a-102">Службы WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="2e42a-102">WCF Data Services 4.5</span></span>
<span data-ttu-id="2e42a-103">Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] (которые раньше назывались ADO.NET Data Services) — это компонент платформы .NET Framework, с помощью которого можно создавать службы, использующие [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для передачи и получения данных через Интернет или интрасеть с помощью семантики [REST](http://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="2e42a-103">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="2e42a-104">Службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] предоставляют данные как ресурсы, адресуемые с помощью URI.</span><span class="sxs-lookup"><span data-stu-id="2e42a-104">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="2e42a-105">Доступ и изменение данных производится с помощью таких стандартных команд HTTP, как GET, PUT, POST и DELETE.</span><span class="sxs-lookup"><span data-stu-id="2e42a-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="2e42a-106">В службах [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] используются соглашения об отношениях сущностей из [модели EDM](../../../../docs/framework/data/adonet/entity-data-model.md) для предоставления ресурсов в виде наборов сущностей, связанных сопоставлениями.</span><span class="sxs-lookup"><span data-stu-id="2e42a-106">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>  
  
 <span data-ttu-id="2e42a-107">При адресации и обновлении ресурсов службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] используют протокол [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e42a-107">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] uses the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol for addressing and updating resources.</span></span> <span data-ttu-id="2e42a-108">В результате доступ к этим службам можно получить из любого клиента, который поддерживает [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e42a-108">In this way, you can access these services from any client that supports [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="2e42a-109"> позволяет осуществлять запросы и запись данных в ресурсы с использованием традиционных форматов передачи: Atom, набора стандартов обмена и обновления данных на основе XML и нотации объектов JavaScript (JSON), текстового формата обмена данными, широко применяемого в приложениях AJAX.</span><span class="sxs-lookup"><span data-stu-id="2e42a-109"> enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="2e42a-110"> позволяет предоставлять данные, поступающие из различных источников, в виде каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e42a-110"> can expose data that originates from various sources as [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span> <span data-ttu-id="2e42a-111">Средства Visual Studio упрощают создание служб на базе [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] за счет использования модели данных ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="2e42a-111">Visual Studio tools make it easier for you to create an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="2e42a-112">Также можно создавать каналы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], основанные на классах CLR, данных с поздним связыванием или данных, не имеющих типа.</span><span class="sxs-lookup"><span data-stu-id="2e42a-112">You can also create [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>  
  
 <span data-ttu-id="2e42a-113">В состав служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] также включен набор клиентских библиотек: одна для типовых клиентских приложений .NET Framework, а другая специально для приложений на основе Silverlight.</span><span class="sxs-lookup"><span data-stu-id="2e42a-113">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="2e42a-114">Данные клиентской библиотеки предоставляют возможности объектно ориентированного программирования для доступа к каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из таких платформ, как .NET Framework и Silverlight.</span><span class="sxs-lookup"><span data-stu-id="2e42a-114">These client libraries provide an object-based programming model when you access an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from environments such as the .NET Framework and Silverlight.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="2e42a-115">Подготовка к изучению темы</span><span class="sxs-lookup"><span data-stu-id="2e42a-115">Where Should I Start?</span></span>  
 <span data-ttu-id="2e42a-116">В зависимости от потребностей, ознакомьтесь с началом работы со службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] в одном из следующих разделов.</span><span class="sxs-lookup"><span data-stu-id="2e42a-116">Depending on your interests, consider getting started with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] in one of the following topics.</span></span>  
  
 <span data-ttu-id="2e42a-117">Необходимо перейти непосредственно к…</span><span class="sxs-lookup"><span data-stu-id="2e42a-117">I want to jump right in…</span></span>  
 -   [<span data-ttu-id="2e42a-118">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="2e42a-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="2e42a-119">Начало работы</span><span class="sxs-lookup"><span data-stu-id="2e42a-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [<span data-ttu-id="2e42a-120">Краткое руководство по Silverlight</span><span class="sxs-lookup"><span data-stu-id="2e42a-120">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="2e42a-121">Краткое руководство по Silverlight для разработчиков Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2e42a-121">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 <span data-ttu-id="2e42a-122">Просто ознакомьте меня с примерами кода…</span><span class="sxs-lookup"><span data-stu-id="2e42a-122">Just show me some code…</span></span>  
 -   [<span data-ttu-id="2e42a-123">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="2e42a-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="2e42a-124">Практическое руководство. Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="2e42a-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [<span data-ttu-id="2e42a-125">Практическое руководство. Привязка данных к элементам Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="2e42a-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 <span data-ttu-id="2e42a-126">Требуются дополнительные сведения о [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span><span class="sxs-lookup"><span data-stu-id="2e42a-126">I want to know more about [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span></span>  
 -   [<span data-ttu-id="2e42a-127">Технический документ. Введение в OData</span><span class="sxs-lookup"><span data-stu-id="2e42a-127">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="2e42a-128">Веб-сайт протокола Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="2e42a-128">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [<span data-ttu-id="2e42a-129">OData SDK</span><span class="sxs-lookup"><span data-stu-id="2e42a-129">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [<span data-ttu-id="2e42a-130">OData: часто задаваемые вопросы</span><span class="sxs-lookup"><span data-stu-id="2e42a-130">OData: Frequently Asked Questions</span></span>](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 <span data-ttu-id="2e42a-131">Хочу посмотреть некоторые видеоматериалы…</span><span class="sxs-lookup"><span data-stu-id="2e42a-131">I want to watch some videos…</span></span>  
 -   [<span data-ttu-id="2e42a-132">Руководство для начинающих по службам данных WCF</span><span class="sxs-lookup"><span data-stu-id="2e42a-132">Beginner's Guide to WCF Data Services</span></span>](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [<span data-ttu-id="2e42a-133">Видеофильмы о службах данных WCF для разработчиков</span><span class="sxs-lookup"><span data-stu-id="2e42a-133">WCF Data Services Developer Videos</span></span>](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [<span data-ttu-id="2e42a-134">OData: веб-сайт разработчиков</span><span class="sxs-lookup"><span data-stu-id="2e42a-134">OData: Developers Web site</span></span>](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 <span data-ttu-id="2e42a-135">Требуются комплексные образцы</span><span class="sxs-lookup"><span data-stu-id="2e42a-135">I want to see end-to-end samples</span></span>  
 -   [<span data-ttu-id="2e42a-136">Образцы документации по службам WCF Data Services в коллекции образцов MSDN</span><span class="sxs-lookup"><span data-stu-id="2e42a-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [<span data-ttu-id="2e42a-137">Другие образцы служб WCF Data Services в коллекции образцов MSDN</span><span class="sxs-lookup"><span data-stu-id="2e42a-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [<span data-ttu-id="2e42a-138">OData SDK</span><span class="sxs-lookup"><span data-stu-id="2e42a-138">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 <span data-ttu-id="2e42a-139">Как происходит интеграция со средствами Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e42a-139">How does it integrate with Visual Studio?</span></span>  
 -   [<span data-ttu-id="2e42a-140">Создание библиотеки клиентов службы данных</span><span class="sxs-lookup"><span data-stu-id="2e42a-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [<span data-ttu-id="2e42a-141">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="2e42a-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [<span data-ttu-id="2e42a-142">Поставщик Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2e42a-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 <span data-ttu-id="2e42a-143">Рекомендуемые действия в этой ситуации</span><span class="sxs-lookup"><span data-stu-id="2e42a-143">What can I do with it?</span></span>  
 -   [<span data-ttu-id="2e42a-144">Обзор набора средств Visual Studio для Unity</span><span class="sxs-lookup"><span data-stu-id="2e42a-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [<span data-ttu-id="2e42a-145">Технический документ. Введение в OData</span><span class="sxs-lookup"><span data-stu-id="2e42a-145">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="2e42a-146">Сценарии приложения</span><span class="sxs-lookup"><span data-stu-id="2e42a-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 <span data-ttu-id="2e42a-147">Необходима информация об использовании Silverlight…</span><span class="sxs-lookup"><span data-stu-id="2e42a-147">I want to use Silverlight…</span></span>  
 -   [<span data-ttu-id="2e42a-148">Краткое руководство по Silverlight</span><span class="sxs-lookup"><span data-stu-id="2e42a-148">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="2e42a-149">Службы WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="2e42a-149">WCF Data Services (Silverlight)</span></span>](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [<span data-ttu-id="2e42a-150">Приступая к работе с Silverlight</span><span class="sxs-lookup"><span data-stu-id="2e42a-150">Getting Started with Silverlight</span></span>](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 <span data-ttu-id="2e42a-151">Я хочу создать приложение Windows Phone…</span><span class="sxs-lookup"><span data-stu-id="2e42a-151">I want to create a Windows Phone application…</span></span>  
 -   [<span data-ttu-id="2e42a-152">Краткое руководство по Silverlight для разработчиков Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2e42a-152">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [<span data-ttu-id="2e42a-153">Клиент протокола OData для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2e42a-153">Open Data Protocol (OData) Client for Windows Phone</span></span>](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 <span data-ttu-id="2e42a-154">Сведения об использовании LINQ…</span><span class="sxs-lookup"><span data-stu-id="2e42a-154">I want to use LINQ…</span></span>  
 -   [<span data-ttu-id="2e42a-155">Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="2e42a-155">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [<span data-ttu-id="2e42a-156">Рекомендации по LINQ</span><span class="sxs-lookup"><span data-stu-id="2e42a-156">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [<span data-ttu-id="2e42a-157">Практическое руководство. Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="2e42a-157">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 <span data-ttu-id="2e42a-158">Необходимы дополнительные сведения...</span><span class="sxs-lookup"><span data-stu-id="2e42a-158">I still need some more information…</span></span>  
 -   [<span data-ttu-id="2e42a-159">Блог группы служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="2e42a-159">WCF Data Services Team Blog</span></span>](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [<span data-ttu-id="2e42a-160">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="2e42a-160">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [<span data-ttu-id="2e42a-161">Центр разработчиков WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="2e42a-161">WCF Data Services Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [<span data-ttu-id="2e42a-162">Веб-сайт протокола Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="2e42a-162">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a><span data-ttu-id="2e42a-163">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2e42a-163">In This Section</span></span>  
 [<span data-ttu-id="2e42a-164">Обзор набора средств Visual Studio для Unity</span><span class="sxs-lookup"><span data-stu-id="2e42a-164">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 <span data-ttu-id="2e42a-165">Содержит общие сведения о функциях и возможностях, доступных в службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e42a-165">Provides an overview of the features and functionality available in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="2e42a-166">Новые возможности служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="2e42a-166">What's New in WCF Data Services</span></span>](http://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 <span data-ttu-id="2e42a-167">Описывает новые возможности в службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] и поддержку новых возможностей [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e42a-167">Describes new functionality in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and support for new [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] features.</span></span>  
  
 [<span data-ttu-id="2e42a-168">Начало работы</span><span class="sxs-lookup"><span data-stu-id="2e42a-168">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 <span data-ttu-id="2e42a-169">Описывает предоставление и получение каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] с помощью [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e42a-169">Describes how to expose and consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds by using [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="2e42a-170">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="2e42a-170">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 <span data-ttu-id="2e42a-171">Описывает создание и настройку службы данных, предоставляющей каналы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e42a-171">Describes how to create and configure a data service that exposes [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="2e42a-172">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="2e42a-172">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 <span data-ttu-id="2e42a-173">Описывает использование клиентских библиотек для использования канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из клиентского приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2e42a-173">Describes how to use client libraries to consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from a .NET Framework client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e42a-174">См. также</span><span class="sxs-lookup"><span data-stu-id="2e42a-174">See Also</span></span>  
 [<span data-ttu-id="2e42a-175">Передача состояния представления (REST)</span><span class="sxs-lookup"><span data-stu-id="2e42a-175">Representational State Transfer (REST)</span></span>](http://go.microsoft.com/fwlink/?LinkId=113919)
