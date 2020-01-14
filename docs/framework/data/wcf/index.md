---
title: Службы WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: aace683b1a105445b5a3ba3de0a6a671859588b5
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937447"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="04d34-102">Службы WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="04d34-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="04d34-103">WCF Data Services (прежнее название — "службы данных ADO.NET") — это компонент .NET Framework, который позволяет создавать службы, использующие Open Data Protocol (OData) для предоставления и использования данных в Интернете или интрасети с помощью семантики [передачи состояния представления (остальное)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span><span class="sxs-lookup"><span data-stu-id="04d34-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span></span> <span data-ttu-id="04d34-104">OData предоставляет доступ к данным в виде ресурсов, которые адресуются по URI.</span><span class="sxs-lookup"><span data-stu-id="04d34-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="04d34-105">Доступ к данным и их изменение осуществляются с помощью стандартных HTTP-команд GET, PUT, POST и DELETE.</span><span class="sxs-lookup"><span data-stu-id="04d34-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="04d34-106">OData использует соглашения об отношениях отношений сущностей [EDM](../adonet/entity-data-model.md) для предоставления ресурсов в виде наборов сущностей, связанных ассоциациями.</span><span class="sxs-lookup"><span data-stu-id="04d34-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="04d34-107">WCF Data Services использует протокол OData для адресации и обновления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="04d34-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="04d34-108">Таким образом, доступ к этим службам можно получить с любого клиента, поддерживающего OData.</span><span class="sxs-lookup"><span data-stu-id="04d34-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="04d34-109">OData позволяет запрашивать и записывать данные в ресурсы с помощью хорошо известных форматов передачи: Atom, набора стандартов для обмена и обновления данных в формате XML, а также нотация объектов JavaScript (JSON), основанный на тексте формат обмена данными, широко применяемый в AJAX. приложений.</span><span class="sxs-lookup"><span data-stu-id="04d34-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="04d34-110">WCF Data Services может предоставлять данные, происходящие из различных источников, в качестве каналов OData.</span><span class="sxs-lookup"><span data-stu-id="04d34-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="04d34-111">Средства Visual Studio облегчают создание службы на основе OData с помощью модели данных ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="04d34-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="04d34-112">Можно также создавать веб-каналы OData на основе классов среды CLR и даже данных с поздним связыванием или нетипизированными данными.</span><span class="sxs-lookup"><span data-stu-id="04d34-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="04d34-113">WCF Data Services также включает набор клиентских библиотек, один для общих .NET Framework клиентских приложений и другой специально для приложений на основе Silverlight.</span><span class="sxs-lookup"><span data-stu-id="04d34-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="04d34-114">Эти клиентские библиотеки предоставляют модель программирования на основе объектов при доступе к каналу OData из таких сред, как .NET Framework и Silverlight.</span><span class="sxs-lookup"><span data-stu-id="04d34-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="04d34-115">Подготовка к изучению темы</span><span class="sxs-lookup"><span data-stu-id="04d34-115">Where Should I Start?</span></span>

<span data-ttu-id="04d34-116">В зависимости от ваших интересов рекомендуется приступить к работе с WCF Data Services в одном из следующих разделов.</span><span class="sxs-lookup"><span data-stu-id="04d34-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="04d34-117">Необходимо перейти непосредственно к…</span><span class="sxs-lookup"><span data-stu-id="04d34-117">I want to jump right in...</span></span>

- [<span data-ttu-id="04d34-118">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="04d34-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="04d34-119">Начало работы</span><span class="sxs-lookup"><span data-stu-id="04d34-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="04d34-120">Просто покажите мне код...</span><span class="sxs-lookup"><span data-stu-id="04d34-120">Just show me some code...</span></span>

- [<span data-ttu-id="04d34-121">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="04d34-121">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="04d34-122">Практическое руководство. Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="04d34-122">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="04d34-123">Практическое руководство. Привязка данных к элементам Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="04d34-123">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="04d34-124">Я хочу узнать больше о OData...</span><span class="sxs-lookup"><span data-stu-id="04d34-124">I want to know more about OData...</span></span>

- [<span data-ttu-id="04d34-125">Технический документ. Введение в OData</span><span class="sxs-lookup"><span data-stu-id="04d34-125">White paper: Introducing OData</span></span>](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [<span data-ttu-id="04d34-126">Веб-сайт Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="04d34-126">Open Data Protocol website</span></span>](https://www.odata.org/)
- [<span data-ttu-id="04d34-127">OData SDK</span><span class="sxs-lookup"><span data-stu-id="04d34-127">OData: SDK</span></span>](https://www.odata.org/ecosystem/)

<span data-ttu-id="04d34-128">Я хочу просмотреть полный пример...</span><span class="sxs-lookup"><span data-stu-id="04d34-128">I want to see end-to-end samples...</span></span>

- <span data-ttu-id="04d34-129">[Краткое руководство по WCF Data Services](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span><span class="sxs-lookup"><span data-stu-id="04d34-129">[WCF Data Services Quickstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span></span>
- [<span data-ttu-id="04d34-130">Пакет SDK OData — пример кода</span><span class="sxs-lookup"><span data-stu-id="04d34-130">OData SDK - Sample Code</span></span>](https://www.odata.org/ecosystem/#sdk)

<span data-ttu-id="04d34-131">Как происходит интеграция со средствами Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04d34-131">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="04d34-132">Создание библиотеки клиентов службы данных</span><span class="sxs-lookup"><span data-stu-id="04d34-132">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="04d34-133">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="04d34-133">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="04d34-134">Поставщик Entity Framework</span><span class="sxs-lookup"><span data-stu-id="04d34-134">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="04d34-135">Рекомендуемые действия в этой ситуации</span><span class="sxs-lookup"><span data-stu-id="04d34-135">What can I do with it?</span></span>

- [<span data-ttu-id="04d34-136">Обзор</span><span class="sxs-lookup"><span data-stu-id="04d34-136">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="04d34-137">Сценарии приложения</span><span class="sxs-lookup"><span data-stu-id="04d34-137">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="04d34-138">Я хочу использовать LINQ...</span><span class="sxs-lookup"><span data-stu-id="04d34-138">I want to use LINQ...</span></span>

- [<span data-ttu-id="04d34-139">Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="04d34-139">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="04d34-140">Рекомендации по LINQ</span><span class="sxs-lookup"><span data-stu-id="04d34-140">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="04d34-141">Практическое руководство. Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="04d34-141">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="04d34-142">Мне по-прежнему нужны дополнительные сведения...</span><span class="sxs-lookup"><span data-stu-id="04d34-142">I still need some more information...</span></span>

- [<span data-ttu-id="04d34-143">Блог группы служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="04d34-143">WCF Data Services Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [<span data-ttu-id="04d34-144">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="04d34-144">Resources</span></span>](wcf-data-services-resources.md)

## <a name="in-this-section"></a><span data-ttu-id="04d34-145">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="04d34-145">In This Section</span></span>

[<span data-ttu-id="04d34-146">Обзор</span><span class="sxs-lookup"><span data-stu-id="04d34-146">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="04d34-147">Содержит общие сведения о функциях и функциях, доступных в WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="04d34-147">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="04d34-148">[Новые возможности WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="04d34-148">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="04d34-149">Описание новых функциональных возможностей WCF Data Services и поддержки новых функций OData.</span><span class="sxs-lookup"><span data-stu-id="04d34-149">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="04d34-150">Начало работы</span><span class="sxs-lookup"><span data-stu-id="04d34-150">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="04d34-151">Описывает, как предоставлять и использовать каналы OData с помощью WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="04d34-151">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="04d34-152">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="04d34-152">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="04d34-153">Описывает создание и настройку службы данных, предоставляющей доступ к каналам OData.</span><span class="sxs-lookup"><span data-stu-id="04d34-153">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="04d34-154">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="04d34-154">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="04d34-155">Описывает использование клиентских библиотек для использования каналов OData из клиентского приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04d34-155">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="04d34-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="04d34-156">See also</span></span>

- [<span data-ttu-id="04d34-157">Передача состояния представления (REST)</span><span class="sxs-lookup"><span data-stu-id="04d34-157">Representational State Transfer (REST)</span></span>](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
