---
title: Службы WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 017fe2177cf824d461b4c51ea805f75b6ddbe064
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779986"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="74ff1-102">Службы WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="74ff1-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="74ff1-103">WCF Data Services (прежнее название — "службы данных ADO.NET") — это компонент .NET Framework, который позволяет создавать службы, использующие [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для предоставления и использования данных в Интернете или интрасети с помощью семантики [состояния представления. Перемещение (остальное)](https://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="74ff1-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="74ff1-104">OData предоставляет доступ к данным в виде ресурсов, которые адресуются по URI.</span><span class="sxs-lookup"><span data-stu-id="74ff1-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="74ff1-105">Доступ и изменение данных производится с помощью таких стандартных команд HTTP, как GET, PUT, POST и DELETE.</span><span class="sxs-lookup"><span data-stu-id="74ff1-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="74ff1-106">OData использует соглашения об отношениях отношений сущностей [EDM](../adonet/entity-data-model.md) для предоставления ресурсов в виде наборов сущностей, связанных ассоциациями.</span><span class="sxs-lookup"><span data-stu-id="74ff1-106">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="74ff1-107">WCF Data Services использует протокол OData для адресации и обновления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="74ff1-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="74ff1-108">Таким образом, доступ к этим службам можно получить с любого клиента, поддерживающего OData.</span><span class="sxs-lookup"><span data-stu-id="74ff1-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="74ff1-109">OData позволяет запрашивать и записывать данные в ресурсы с помощью хорошо известных форматов перемещения: Atom, набор стандартов для обмена и обновления данных в формате XML и нотация объектов JavaScript (JSON), текстовый формат обмена данными, широко применяемый в приложениях AJAX.</span><span class="sxs-lookup"><span data-stu-id="74ff1-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="74ff1-110">WCF Data Services может предоставлять данные, происходящие из различных источников, в качестве каналов OData.</span><span class="sxs-lookup"><span data-stu-id="74ff1-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="74ff1-111">Средства Visual Studio облегчают создание службы на основе OData с помощью модели данных ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="74ff1-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="74ff1-112">Можно также создавать веб-каналы OData на основе классов среды CLR и даже данных с поздним связыванием или нетипизированными данными.</span><span class="sxs-lookup"><span data-stu-id="74ff1-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="74ff1-113">WCF Data Services также включает набор клиентских библиотек, один для общих .NET Framework клиентских приложений и другой специально для приложений на основе Silverlight.</span><span class="sxs-lookup"><span data-stu-id="74ff1-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="74ff1-114">Эти клиентские библиотеки предоставляют модель программирования на основе объектов при доступе к каналу OData из таких сред, как .NET Framework и Silverlight.</span><span class="sxs-lookup"><span data-stu-id="74ff1-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="74ff1-115">Подготовка к изучению темы</span><span class="sxs-lookup"><span data-stu-id="74ff1-115">Where Should I Start?</span></span>

<span data-ttu-id="74ff1-116">В зависимости от ваших интересов рекомендуется приступить к работе с WCF Data Services в одном из следующих разделов.</span><span class="sxs-lookup"><span data-stu-id="74ff1-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="74ff1-117">Необходимо перейти непосредственно к…</span><span class="sxs-lookup"><span data-stu-id="74ff1-117">I want to jump right in...</span></span>

- [<span data-ttu-id="74ff1-118">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="74ff1-118">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="74ff1-119">Начало работы</span><span class="sxs-lookup"><span data-stu-id="74ff1-119">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

- [<span data-ttu-id="74ff1-120">Краткое руководство по Silverlight</span><span class="sxs-lookup"><span data-stu-id="74ff1-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="74ff1-121">Краткое руководство по Silverlight для разработчиков Windows Phone</span><span class="sxs-lookup"><span data-stu-id="74ff1-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="74ff1-122">Просто покажите мне код...</span><span class="sxs-lookup"><span data-stu-id="74ff1-122">Just show me some code...</span></span>

- [<span data-ttu-id="74ff1-123">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="74ff1-123">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="74ff1-124">Практическое руководство. Выполнение запросов службы данных</span><span class="sxs-lookup"><span data-stu-id="74ff1-124">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="74ff1-125">Практическое руководство. Привязка данных к Windows Presentation Foundation элементам</span><span class="sxs-lookup"><span data-stu-id="74ff1-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="74ff1-126">Я хочу узнать больше о OData...</span><span class="sxs-lookup"><span data-stu-id="74ff1-126">I want to know more about OData...</span></span>

- [<span data-ttu-id="74ff1-127">Технический документ Знакомство с OData</span><span class="sxs-lookup"><span data-stu-id="74ff1-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="74ff1-128">Веб-сайт протокола Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="74ff1-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

- [<span data-ttu-id="74ff1-129">Протокола TOOL</span><span class="sxs-lookup"><span data-stu-id="74ff1-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

- [<span data-ttu-id="74ff1-130">Протокола Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="74ff1-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="74ff1-131">Я хочу посмотреть некоторые видео...</span><span class="sxs-lookup"><span data-stu-id="74ff1-131">I want to watch some videos...</span></span>

- [<span data-ttu-id="74ff1-132">Руководство для начинающих по службам данных WCF</span><span class="sxs-lookup"><span data-stu-id="74ff1-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

- [<span data-ttu-id="74ff1-133">Видеофильмы о службах данных WCF для разработчиков</span><span class="sxs-lookup"><span data-stu-id="74ff1-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

- [<span data-ttu-id="74ff1-134">Протокола Веб-сайт разработчиков</span><span class="sxs-lookup"><span data-stu-id="74ff1-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="74ff1-135">Я хочу просмотреть полный пример...</span><span class="sxs-lookup"><span data-stu-id="74ff1-135">I want to see end-to-end samples...</span></span>

- [<span data-ttu-id="74ff1-136">Образцы документации по службам WCF Data Services в коллекции образцов MSDN</span><span class="sxs-lookup"><span data-stu-id="74ff1-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

- [<span data-ttu-id="74ff1-137">Другие образцы служб WCF Data Services в коллекции образцов MSDN</span><span class="sxs-lookup"><span data-stu-id="74ff1-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

- [<span data-ttu-id="74ff1-138">Протокола TOOL</span><span class="sxs-lookup"><span data-stu-id="74ff1-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="74ff1-139">Как происходит интеграция со средствами Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74ff1-139">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="74ff1-140">Создание библиотеки клиентов службы данных</span><span class="sxs-lookup"><span data-stu-id="74ff1-140">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="74ff1-141">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="74ff1-141">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="74ff1-142">Поставщик Entity Framework</span><span class="sxs-lookup"><span data-stu-id="74ff1-142">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="74ff1-143">Рекомендуемые действия в этой ситуации</span><span class="sxs-lookup"><span data-stu-id="74ff1-143">What can I do with it?</span></span>

- [<span data-ttu-id="74ff1-144">Обзор</span><span class="sxs-lookup"><span data-stu-id="74ff1-144">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="74ff1-145">Технический документ Знакомство с OData</span><span class="sxs-lookup"><span data-stu-id="74ff1-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

- [<span data-ttu-id="74ff1-146">Сценарии приложения</span><span class="sxs-lookup"><span data-stu-id="74ff1-146">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="74ff1-147">Я хочу использовать Silverlight...</span><span class="sxs-lookup"><span data-stu-id="74ff1-147">I want to use Silverlight...</span></span>

- [<span data-ttu-id="74ff1-148">Краткое руководство по Silverlight</span><span class="sxs-lookup"><span data-stu-id="74ff1-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

- [<span data-ttu-id="74ff1-149">Службы WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="74ff1-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

- [<span data-ttu-id="74ff1-150">Приступая к работе с Silverlight</span><span class="sxs-lookup"><span data-stu-id="74ff1-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="74ff1-151">Я хочу использовать LINQ...</span><span class="sxs-lookup"><span data-stu-id="74ff1-151">I want to use LINQ...</span></span>

- [<span data-ttu-id="74ff1-152">Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="74ff1-152">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="74ff1-153">Рекомендации по LINQ</span><span class="sxs-lookup"><span data-stu-id="74ff1-153">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="74ff1-154">Практическое руководство. Выполнение запросов службы данных</span><span class="sxs-lookup"><span data-stu-id="74ff1-154">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="74ff1-155">Мне по-прежнему нужны дополнительные сведения...</span><span class="sxs-lookup"><span data-stu-id="74ff1-155">I still need some more information...</span></span>

- [<span data-ttu-id="74ff1-156">Блог группы служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="74ff1-156">WCF Data Services Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=150511)

- [<span data-ttu-id="74ff1-157">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="74ff1-157">Resources</span></span>](wcf-data-services-resources.md)

- [<span data-ttu-id="74ff1-158">Центр разработчиков WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="74ff1-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

- [<span data-ttu-id="74ff1-159">Веб-сайт протокола Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="74ff1-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="74ff1-160">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="74ff1-160">In This Section</span></span>

[<span data-ttu-id="74ff1-161">Обзор</span><span class="sxs-lookup"><span data-stu-id="74ff1-161">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="74ff1-162">Содержит общие сведения о функциях и функциях, доступных в WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="74ff1-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="74ff1-163">[Новые возможности WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="74ff1-163">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="74ff1-164">Описание новых функциональных возможностей WCF Data Services и поддержки новых функций OData.</span><span class="sxs-lookup"><span data-stu-id="74ff1-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="74ff1-165">Начало работы</span><span class="sxs-lookup"><span data-stu-id="74ff1-165">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="74ff1-166">Описывает, как предоставлять и использовать каналы OData с помощью WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="74ff1-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="74ff1-167">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="74ff1-167">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="74ff1-168">Описывает создание и настройку службы данных, предоставляющей доступ к каналам OData.</span><span class="sxs-lookup"><span data-stu-id="74ff1-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="74ff1-169">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="74ff1-169">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="74ff1-170">Описывает использование клиентских библиотек для использования каналов OData из клиентского приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="74ff1-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="74ff1-171">См. также</span><span class="sxs-lookup"><span data-stu-id="74ff1-171">See also</span></span>

- [<span data-ttu-id="74ff1-172">Передача состояния представления (REST)</span><span class="sxs-lookup"><span data-stu-id="74ff1-172">Representational State Transfer (REST)</span></span>](https://go.microsoft.com/fwlink/?LinkId=113919)
