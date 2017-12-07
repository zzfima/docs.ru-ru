---
title: "Разработка современных веб-приложений с помощью ASP.NET Core и Azure"
description: "Разработка современных веб-приложений с помощью ASP.NET Core и Azure | Введение"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 93a74bb7ba537d3c7c0291f7903112dc470133a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="16b84-103">Разработка современных веб-приложений с помощью ASP.NET Core и Azure</span><span class="sxs-lookup"><span data-stu-id="16b84-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

<span data-ttu-id="16b84-104">.NET Core и ASP.NET Core имеют ряд преимуществ по сравнению с традиционной разработкой .NET.</span><span class="sxs-lookup"><span data-stu-id="16b84-104">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="16b84-105">Используйте .NET Core для серверных приложений, если для их успешной работы вам важны некоторые или все приведенные далее аспекты:</span><span class="sxs-lookup"><span data-stu-id="16b84-105">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

-   <span data-ttu-id="16b84-106">Поддержка разных платформ</span><span class="sxs-lookup"><span data-stu-id="16b84-106">Cross-platform support</span></span>

-   <span data-ttu-id="16b84-107">Использование микрослужб</span><span class="sxs-lookup"><span data-stu-id="16b84-107">Use of microservices</span></span>

-   <span data-ttu-id="16b84-108">Использование контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="16b84-108">Use of Docker containers</span></span>

-   <span data-ttu-id="16b84-109">Требования к обеспечению высокой производительности и масштабируемости</span><span class="sxs-lookup"><span data-stu-id="16b84-109">High performance and scalability requirements</span></span>

-   <span data-ttu-id="16b84-110">Параллельное управление версиями приложения .NET на одном сервере</span><span class="sxs-lookup"><span data-stu-id="16b84-110">Side-by-side versioning of .NET versions by application on the same server</span></span>

<span data-ttu-id="16b84-111">Эти требования поддерживаются традиционными приложениями .NET, однако оптимизированные платформы ASP.NET Core и .NET Core обеспечивают улучшенную поддержку указанных выше сценариев.</span><span class="sxs-lookup"><span data-stu-id="16b84-111">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="16b84-112">Все больше организаций предпочитают размещать свои веб-приложения в облаке с помощью таких служб, как Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="16b84-112">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="16b84-113">Рекомендуется рассмотреть возможность размещения приложения в облаке, если для приложения или организации важны следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="16b84-113">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

-   <span data-ttu-id="16b84-114">Сокращение инвестиций в центр обработки данных (оборудование, программное обеспечение, помещения, коммунальные услуги и т. д.)</span><span class="sxs-lookup"><span data-stu-id="16b84-114">Reduced investment in data center costs (hardware, software, space, utilities, etc)</span></span>

-   <span data-ttu-id="16b84-115">Гибкие цены (оплата за фактически используемые, а не простаивающие ресурсы)</span><span class="sxs-lookup"><span data-stu-id="16b84-115">Flexible pricing (pay based on usage, not for idle capacity)</span></span>

-   <span data-ttu-id="16b84-116">Исключительная надежность</span><span class="sxs-lookup"><span data-stu-id="16b84-116">Extreme reliability</span></span>

-   <span data-ttu-id="16b84-117">Улучшенная мобильность приложений, простота изменения места и способа их развертывания</span><span class="sxs-lookup"><span data-stu-id="16b84-117">Improved app mobility; easily change where and how your app is deployed</span></span>

-   <span data-ttu-id="16b84-118">Гибкая емкость, масштабирование в соответствии с фактическими потребностями</span><span class="sxs-lookup"><span data-stu-id="16b84-118">Flexible capacity; scale up or down based on actual needs</span></span>

<span data-ttu-id="16b84-119">Создание веб-приложений с помощью ASP.NET Core, размещенных в Microsoft Azure, характеризуется многочисленными конкурентными преимуществами по сравнению с традиционными альтернативами.</span><span class="sxs-lookup"><span data-stu-id="16b84-119">Building web applications with ASP.NET Core, hosted in Microsoft Azure, offers numerous competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="16b84-120">Платформа ASP.NET Core оптимизирована для современных методик разработки веб-приложений и сценариев размещения в облаке.</span><span class="sxs-lookup"><span data-stu-id="16b84-120">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="16b84-121">В этом руководстве вы узнаете, как спроектировать приложения ASP.NET Core, чтобы максимально эффективно воспользоваться этими возможностями.</span><span class="sxs-lookup"><span data-stu-id="16b84-121">In this guide, you will learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="16b84-122">Назначение</span><span class="sxs-lookup"><span data-stu-id="16b84-122">Purpose</span></span>

<span data-ttu-id="16b84-123">Этот документ является полным руководством по созданию монолитных веб-приложений с помощью ASP.NET Core и Azure.</span><span class="sxs-lookup"><span data-stu-id="16b84-123">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="16b84-124">Это руководство дополняет документ *Проектирование и разработка контейнерных приложений и приложений на основе микрослужб в .NET*, в котором более подробно рассматриваются Docker, микрослужбы и процедура развертывания контейнеров для размещения корпоративных приложений.</span><span class="sxs-lookup"><span data-stu-id="16b84-124">This guide is complementary to the "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a><span data-ttu-id="16b84-125">Проектирование и разработка контейнерных приложений и приложений на основе микрослужб в .NET</span><span class="sxs-lookup"><span data-stu-id="16b84-125">Architecting and Developing Containerized Microservice Based Apps in .NET</span></span>
> - <span data-ttu-id="16b84-126">**электронная книга**</span><span class="sxs-lookup"><span data-stu-id="16b84-126">**e-book**</span></span>  
> <span data-ttu-id="16b84-127"><http://aka.ms/MicroservicesEbook></span><span class="sxs-lookup"><span data-stu-id="16b84-127"><http://aka.ms/MicroservicesEbook></span></span>
> - <span data-ttu-id="16b84-128">**Пример приложения**</span><span class="sxs-lookup"><span data-stu-id="16b84-128">**Sample Application**</span></span>  
> <span data-ttu-id="16b84-129"><http://aka.ms/microservicesarchitecture></span><span class="sxs-lookup"><span data-stu-id="16b84-129"><http://aka.ms/microservicesarchitecture></span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="16b84-130">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="16b84-130">Who should use this guide</span></span>

<span data-ttu-id="16b84-131">Это руководство предназначено главным образом для разработчиков, руководителей отделов разработки и архитекторов, заинтересованных в создании современных веб-приложений с помощью технологий и служб Майкрософт в облаке.</span><span class="sxs-lookup"><span data-stu-id="16b84-131">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="16b84-132">Вторичной аудиторией являются лица, ответственные за принятие технических решений, которые уже знакомы с ASP.NET и (или) Azure и которым требуются сведения о целесообразности обновления до ASP.NET Core для разработки новых и поддержки существующих проектов.</span><span class="sxs-lookup"><span data-stu-id="16b84-132">A secondary audience is technical decision makers who are already familiar ASP.NET and/or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="16b84-133">Как использовать это руководство</span><span class="sxs-lookup"><span data-stu-id="16b84-133">How you can use this guide</span></span>

<span data-ttu-id="16b84-134">Это руководство было сведено в относительно небольшой документ, в котором основное внимание уделяется созданию веб-приложений с помощью современных технологий .NET и Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="16b84-134">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="16b84-135">Поэтому, чтобы получить базовое представление о таких приложениях и разобраться в соответствующих технических рекомендациях, изучите документ полностью.</span><span class="sxs-lookup"><span data-stu-id="16b84-135">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="16b84-136">Это руководство вместе с примером приложения может быть хорошей отправной точкой или полезным справочным документом.</span><span class="sxs-lookup"><span data-stu-id="16b84-136">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="16b84-137">Используйте приведенный пример приложения в качестве шаблона для собственных приложений, или чтобы увидеть, каким образом можно организовать составные части приложения.</span><span class="sxs-lookup"><span data-stu-id="16b84-137">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="16b84-138">Принимая решение о применении этих вариантов к своему приложению, вы всегда можете обратиться к описанным в руководстве принципам и направлениям архитектуры и технологическим возможностям.</span><span class="sxs-lookup"><span data-stu-id="16b84-138">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when weighing these choices for your own application.</span></span>

<span data-ttu-id="16b84-139">При необходимости вы можете порекомендовать это руководство членам своей команды, чтобы и они были в курсе всех важных аспектов.</span><span class="sxs-lookup"><span data-stu-id="16b84-139">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="16b84-140">Если все заинтересованные лица будут использовать общий набор терминологии и придерживаться основополагающих принципов, архитектурные модели и практики будут применяться более последовательно.</span><span class="sxs-lookup"><span data-stu-id="16b84-140">Having everybody working from a common set of terminology and underlying principles will help ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="16b84-141">Ссылки</span><span class="sxs-lookup"><span data-stu-id="16b84-141">References</span></span>
- <span data-ttu-id="16b84-142">**Выбор между .NET Core и .NET Framework для серверных приложений**</span><span class="sxs-lookup"><span data-stu-id="16b84-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
<span data-ttu-id="16b84-143"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="16b84-143"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="16b84-144">[Далее] (modern-web-applications-characteristics.md)</span><span class="sxs-lookup"><span data-stu-id="16b84-144">[Next] (modern-web-applications-characteristics.md)</span></span>
