---
title: "Разработка современных веб-приложений с помощью ASP.NET Core и Azure"
description: "Разработка современных веб-приложений с помощью ASP.NET Core и Azure | Введение"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: db9f0ddd875df1f84bcc5681ee1383b0185f8b7e
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2018
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="d3973-103">Разработка современных веб-приложений с помощью ASP.NET Core и Azure</span><span class="sxs-lookup"><span data-stu-id="d3973-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![изображение обложки](./media/cover.jpg)


<span data-ttu-id="d3973-105">.NET Core и ASP.NET Core имеют ряд преимуществ по сравнению с традиционной разработкой .NET.</span><span class="sxs-lookup"><span data-stu-id="d3973-105">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="d3973-106">Используйте .NET Core для серверных приложений, если для их успешной работы вам важны некоторые или все приведенные далее аспекты:</span><span class="sxs-lookup"><span data-stu-id="d3973-106">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

-   <span data-ttu-id="d3973-107">Поддержка разных платформ</span><span class="sxs-lookup"><span data-stu-id="d3973-107">Cross-platform support</span></span>

-   <span data-ttu-id="d3973-108">Использование микрослужб</span><span class="sxs-lookup"><span data-stu-id="d3973-108">Use of microservices</span></span>

-   <span data-ttu-id="d3973-109">Использование контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="d3973-109">Use of Docker containers</span></span>

-   <span data-ttu-id="d3973-110">Требования к обеспечению высокой производительности и масштабируемости</span><span class="sxs-lookup"><span data-stu-id="d3973-110">High performance and scalability requirements</span></span>

-   <span data-ttu-id="d3973-111">Параллельное управление версиями приложения .NET на одном сервере</span><span class="sxs-lookup"><span data-stu-id="d3973-111">Side-by-side versioning of .NET versions by application on the same server</span></span>

<span data-ttu-id="d3973-112">Эти требования поддерживаются традиционными приложениями .NET, однако оптимизированные платформы ASP.NET Core и .NET Core обеспечивают улучшенную поддержку указанных выше сценариев.</span><span class="sxs-lookup"><span data-stu-id="d3973-112">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="d3973-113">Все больше организаций предпочитают размещать свои веб-приложения в облаке с помощью таких служб, как Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="d3973-113">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="d3973-114">Рекомендуется рассмотреть возможность размещения приложения в облаке, если для приложения или организации важны следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="d3973-114">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

-   <span data-ttu-id="d3973-115">Сокращение инвестиций в центр обработки данных (оборудование, программное обеспечение, помещения, коммунальные услуги и т. д.)</span><span class="sxs-lookup"><span data-stu-id="d3973-115">Reduced investment in data center costs (hardware, software, space, utilities, etc)</span></span>

-   <span data-ttu-id="d3973-116">Гибкие цены (оплата за фактически используемые, а не простаивающие ресурсы)</span><span class="sxs-lookup"><span data-stu-id="d3973-116">Flexible pricing (pay based on usage, not for idle capacity)</span></span>

-   <span data-ttu-id="d3973-117">Исключительная надежность</span><span class="sxs-lookup"><span data-stu-id="d3973-117">Extreme reliability</span></span>

-   <span data-ttu-id="d3973-118">Улучшенная мобильность приложений, простота изменения места и способа их развертывания</span><span class="sxs-lookup"><span data-stu-id="d3973-118">Improved app mobility; easily change where and how your app is deployed</span></span>

-   <span data-ttu-id="d3973-119">Гибкая емкость, масштабирование в соответствии с фактическими потребностями</span><span class="sxs-lookup"><span data-stu-id="d3973-119">Flexible capacity; scale up or down based on actual needs</span></span>

<span data-ttu-id="d3973-120">Создание веб-приложений с помощью ASP.NET Core, размещенных в Microsoft Azure, характеризуется многочисленными конкурентными преимуществами по сравнению с традиционными альтернативами.</span><span class="sxs-lookup"><span data-stu-id="d3973-120">Building web applications with ASP.NET Core, hosted in Microsoft Azure, offers numerous competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="d3973-121">Платформа ASP.NET Core оптимизирована для современных методик разработки веб-приложений и сценариев размещения в облаке.</span><span class="sxs-lookup"><span data-stu-id="d3973-121">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="d3973-122">В этом руководстве вы узнаете, как спроектировать приложения ASP.NET Core, чтобы максимально эффективно воспользоваться этими возможностями.</span><span class="sxs-lookup"><span data-stu-id="d3973-122">In this guide, you will learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="d3973-123">Цель</span><span class="sxs-lookup"><span data-stu-id="d3973-123">Purpose</span></span>

<span data-ttu-id="d3973-124">Этот документ является полным руководством по созданию монолитных веб-приложений с помощью ASP.NET Core и Azure.</span><span class="sxs-lookup"><span data-stu-id="d3973-124">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="d3973-125">Это руководство дополняет документ *Проектирование и разработка контейнерных приложений и приложений на основе микрослужб в .NET*, в котором более подробно рассматриваются Docker, микрослужбы и процедура развертывания контейнеров для размещения корпоративных приложений.</span><span class="sxs-lookup"><span data-stu-id="d3973-125">This guide is complementary to the "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a><span data-ttu-id="d3973-126">Проектирование и разработка контейнерных приложений и приложений на основе микрослужб в .NET</span><span class="sxs-lookup"><span data-stu-id="d3973-126">Architecting and Developing Containerized Microservice Based Apps in .NET</span></span>
> - <span data-ttu-id="d3973-127">**электронная книга**</span><span class="sxs-lookup"><span data-stu-id="d3973-127">**e-book**</span></span>  
> <span data-ttu-id="d3973-128"><http://aka.ms/MicroservicesEbook></span><span class="sxs-lookup"><span data-stu-id="d3973-128"><http://aka.ms/MicroservicesEbook></span></span>
> - <span data-ttu-id="d3973-129">**Пример приложения**</span><span class="sxs-lookup"><span data-stu-id="d3973-129">**Sample Application**</span></span>  
> <span data-ttu-id="d3973-130"><http://aka.ms/microservicesarchitecture></span><span class="sxs-lookup"><span data-stu-id="d3973-130"><http://aka.ms/microservicesarchitecture></span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="d3973-131">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="d3973-131">Who should use this guide</span></span>

<span data-ttu-id="d3973-132">Это руководство предназначено главным образом для разработчиков, руководителей отделов разработки и архитекторов, заинтересованных в создании современных веб-приложений с помощью технологий и служб Майкрософт в облаке.</span><span class="sxs-lookup"><span data-stu-id="d3973-132">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="d3973-133">Вторичной аудиторией являются лица, ответственные за принятие технических решений, которые уже знакомы с ASP.NET и (или) Azure и которым требуются сведения о целесообразности обновления до ASP.NET Core для разработки новых и поддержки существующих проектов.</span><span class="sxs-lookup"><span data-stu-id="d3973-133">A secondary audience is technical decision makers who are already familiar ASP.NET and/or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="d3973-134">Как использовать это руководство</span><span class="sxs-lookup"><span data-stu-id="d3973-134">How you can use this guide</span></span>

<span data-ttu-id="d3973-135">Это руководство было сведено в относительно небольшой документ, в котором основное внимание уделяется созданию веб-приложений с помощью современных технологий .NET и Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="d3973-135">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="d3973-136">Поэтому, чтобы получить базовое представление о таких приложениях и разобраться в соответствующих технических рекомендациях, изучите документ полностью.</span><span class="sxs-lookup"><span data-stu-id="d3973-136">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="d3973-137">Это руководство вместе с примером приложения может быть хорошей отправной точкой или полезным справочным документом.</span><span class="sxs-lookup"><span data-stu-id="d3973-137">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="d3973-138">Используйте приведенный пример приложения в качестве шаблона для собственных приложений, или чтобы увидеть, каким образом можно организовать составные части приложения.</span><span class="sxs-lookup"><span data-stu-id="d3973-138">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="d3973-139">Принимая решение о применении этих вариантов к своему приложению, вы всегда можете обратиться к описанным в руководстве принципам и направлениям архитектуры и технологическим возможностям.</span><span class="sxs-lookup"><span data-stu-id="d3973-139">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when weighing these choices for your own application.</span></span>

<span data-ttu-id="d3973-140">При необходимости вы можете порекомендовать это руководство членам своей команды, чтобы и они были в курсе всех важных аспектов.</span><span class="sxs-lookup"><span data-stu-id="d3973-140">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="d3973-141">Если все заинтересованные лица будут использовать общий набор терминологии и придерживаться основополагающих принципов, архитектурные модели и практики будут применяться более последовательно.</span><span class="sxs-lookup"><span data-stu-id="d3973-141">Having everybody working from a common set of terminology and underlying principles will help ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="d3973-142">Ссылки</span><span class="sxs-lookup"><span data-stu-id="d3973-142">References</span></span>
- <span data-ttu-id="d3973-143">**Выбор между .NET Core и .NET Framework для серверных приложений**</span><span class="sxs-lookup"><span data-stu-id="d3973-143">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
<span data-ttu-id="d3973-144"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="d3973-144"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="d3973-145">[Далее] (modern-web-applications-characteristics.md)</span><span class="sxs-lookup"><span data-stu-id="d3973-145">[Next] (modern-web-applications-characteristics.md)</span></span>
