---
title: Микрослужбы .NET. Архитектура контейнерных приложений .NET
description: 'Микрослужбы .NET: архитектура контейнерных приложений .NET | Микрослужбы — это модульные службы, развертываемые независимо друг от друга. Контейнеры Docker (для Linux и Windows) упрощают развертывание и тестирование путем объединения службы и ее зависимостей в единый модуль, запускаемый в изолированной среде.'
ms.date: 01/07/2019
ms.openlocfilehash: 7fa4935fe56ca873a5311812637964083e34170e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089914"
---
# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="4aef2-105">Микрослужбы .NET: Архитектура контейнерных приложений .NET</span><span class="sxs-lookup"><span data-stu-id="4aef2-105">.NET Microservices: Architecture for Containerized .NET Applications</span></span>

![Обложка книги](./media/cover-small.png)

<span data-ttu-id="4aef2-107">**ВЫПУСК v2.2** — обновлен до ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="4aef2-107">**EDITION v2.2** - Updated to ASP.NET Core 2.2</span></span>

<span data-ttu-id="4aef2-108">В этом руководстве приводятся общие сведения о разработке приложений на основе микрослужб и управлении ими с помощью контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4aef2-108">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="4aef2-109">В нем рассматриваются подходы к проектированию и реализации архитектуры с помощью .NET Core и контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="4aef2-109">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span>

<span data-ttu-id="4aef2-110">Чтобы вам было проще приступить к работе, в руководстве подробно изучается пример контейнерного приложения на основе микрослужб.</span><span class="sxs-lookup"><span data-stu-id="4aef2-110">To make it easier to get started, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="4aef2-111">Образец приложения доступен в репозитории GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="4aef2-111">The reference application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

## <a name="action-links"></a><span data-ttu-id="4aef2-112">Ссылки действий</span><span class="sxs-lookup"><span data-stu-id="4aef2-112">Action links</span></span>

- <span data-ttu-id="4aef2-113">Скачайте эту электронную книгу в выбранном формате (только на английском языке): | [PDF](https://aka.ms/microservicesebook) | [MOBI](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook-mobi) | [EPUB](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook-epub) |</span><span class="sxs-lookup"><span data-stu-id="4aef2-113">Download this e-book in your format of choice (English version only): | [PDF](https://aka.ms/microservicesebook) | [MOBI](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook-mobi) | [EPUB](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook-epub) |</span></span>

- <span data-ttu-id="4aef2-114">Клонировать эталонное приложение [eShopOnContainers на GitHub](https://github.com/dotnet-architecture/eShopOnContainers) или создать для него вилку</span><span class="sxs-lookup"><span data-stu-id="4aef2-114">Clone/Fork the reference application [eShopOnContainers on GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span></span>

- <span data-ttu-id="4aef2-115">Просмотреть [вводный видеоролик на канале Channel 9](https://aka.ms/microservices-video)</span><span class="sxs-lookup"><span data-stu-id="4aef2-115">Watch the [introductory video on Channel 9](https://aka.ms/microservices-video)</span></span>

- <span data-ttu-id="4aef2-116">Быстрое знакомство с [архитектурой микрослужб](https://aka.ms/MicroservicesArchitecture)</span><span class="sxs-lookup"><span data-stu-id="4aef2-116">Get to know the [Microservices Architecture](https://aka.ms/MicroservicesArchitecture) right away</span></span>

## <a name="introduction"></a><span data-ttu-id="4aef2-117">Вступление</span><span class="sxs-lookup"><span data-stu-id="4aef2-117">Introduction</span></span>

<span data-ttu-id="4aef2-118">Предприятия все шире применяют контейнеры с целью сэкономить средства, решить проблемы, возникающие при разработке решений, и оптимизировать процессы разработки и рабочие операции.</span><span class="sxs-lookup"><span data-stu-id="4aef2-118">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="4aef2-119">Корпорация Майкрософт развивает технологии в области контейнеров для Windows и Linux, создавая такие продукты, как Служба Azure Kubernetes и Azure Service Fabric, и сотрудничая с ведущими в отрасли компаниями, такими как Docker, Mesosphere и Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="4aef2-119">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Kubernetes Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="4aef2-120">С помощью этих решений для работы с контейнерами организации могут создавать и развертывать приложения с той же скоростью и масштабируемостью, что и в облачной среде, на основе любых платформ и средств.</span><span class="sxs-lookup"><span data-stu-id="4aef2-120">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="4aef2-121">Docker становится стандартом де-факто в области контейнеризации приложений. Это решение поддерживается большинством поставщиков в экосистеме Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="4aef2-121">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="4aef2-122">(Корпорация Майкрософт — один из основных поставщиков облачных решений, поддерживающих Docker.) В будущем Docker, вероятно, можно будет встретить в любом центре обработки данных как в облаке, так и в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="4aef2-122">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="4aef2-123">Помимо этого, развивается архитектура [микрослужб](https://martinfowler.com/articles/microservices.html), которая представляет собой важный подход к реализации распределенных критически важных приложений.</span><span class="sxs-lookup"><span data-stu-id="4aef2-123">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="4aef2-124">Архитектура на основе микрослужб предполагает создание приложения на базе коллекции служб, которые могут разрабатываться, тестироваться, развертываться и обновляться независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="4aef2-124">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="4aef2-125">Об этом руководстве</span><span class="sxs-lookup"><span data-stu-id="4aef2-125">About this guide</span></span>

<span data-ttu-id="4aef2-126">В этом руководстве приводятся общие сведения о разработке приложений на основе микрослужб и управлении ими с помощью контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4aef2-126">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="4aef2-127">В нем рассматриваются подходы к проектированию и реализации архитектуры с помощью .NET Core и контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="4aef2-127">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="4aef2-128">Чтобы вам было проще приступить к работе с контейнерами и микрослужбами, в руководстве подробно изучается пример контейнерного приложения на основе микрослужб.</span><span class="sxs-lookup"><span data-stu-id="4aef2-128">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="4aef2-129">Пример приложения доступен в репозитории GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="4aef2-129">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="4aef2-130">В этом руководстве приведены базовые принципы разработки и архитектуры, в первую очередь — на уровне среды разработки. Основное внимание уделяется двум технологиям: Docker и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4aef2-130">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="4aef2-131">Мы ставили себе целью, чтобы при чтении этого руководства вы могли сосредоточиться на проектировании приложения, не задумываясь об инфраструктуре рабочей среды (облачной или локальной).</span><span class="sxs-lookup"><span data-stu-id="4aef2-131">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="4aef2-132">Принимать решения, связанные с инфраструктурой, вы будете позднее при создании приложений, готовых к использованию в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="4aef2-132">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="4aef2-133">Таким образом, это руководство ориентировано на среду разработки без учета особенностей инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="4aef2-133">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="4aef2-134">После изучения этого руководства вашим следующим шагом будет изучение готовых к использованию микрослужб в Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="4aef2-134">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="version"></a><span data-ttu-id="4aef2-135">Version</span><span class="sxs-lookup"><span data-stu-id="4aef2-135">Version</span></span>

<span data-ttu-id="4aef2-136">Руководство обновлено в соответствии с версией **.NET Core 2.2** и включает множество дополнений по тому же "поколению" технологий (то есть,</span><span class="sxs-lookup"><span data-stu-id="4aef2-136">This guide has been revised to cover **.NET Core 2.2** version plus many additional updates related to the same “wave” of technologies (that is.</span></span> <span data-ttu-id="4aef2-137">технологий Azure и сторонних производителей), к которому относится .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="4aef2-137">Azure and additional 3rd party technologies) coinciding in time with .NET Core 2.2.</span></span> <span data-ttu-id="4aef2-138">В связи с этим книга теперь также получила версию издания **2.2**.</span><span class="sxs-lookup"><span data-stu-id="4aef2-138">That’s why the book version has also been updated to version **2.2**.</span></span>

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="4aef2-139">Темы, которые выходят за рамки этого руководства</span><span class="sxs-lookup"><span data-stu-id="4aef2-139">What this guide does not cover</span></span>

<span data-ttu-id="4aef2-140">В этом руководстве не рассматриваются такие вопросы, как жизненный цикл приложения, DevOps, конвейеры непрерывной интеграции и непрерывного развертывания, а также совместная работа.</span><span class="sxs-lookup"><span data-stu-id="4aef2-140">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="4aef2-141">Эти темы обсуждаются в дополнительном руководстве [Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт](https://aka.ms/dockerlifecycleebook).</span><span class="sxs-lookup"><span data-stu-id="4aef2-141">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="4aef2-142">В настоящем руководстве также не приводятся сведения о реализации инфраструктуры Azure, например информация о конкретных оркестраторах.</span><span class="sxs-lookup"><span data-stu-id="4aef2-142">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4aef2-143">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="4aef2-143">Additional resources</span></span>

- <span data-ttu-id="4aef2-144">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт) (электронная книга, доступная для скачивания)</span><span class="sxs-lookup"><span data-stu-id="4aef2-144">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book)</span></span>  
    <https://aka.ms/dockerlifecycleebook>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="4aef2-145">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="4aef2-145">Who should use this guide</span></span>

<span data-ttu-id="4aef2-146">Мы создали это руководство для разработчиков и архитекторов решений, которые не имеют опыта разработки приложений на основе Docker и работы с архитектурой микрослужб.</span><span class="sxs-lookup"><span data-stu-id="4aef2-146">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="4aef2-147">Воспользуйтесь этим руководством, чтобы узнать, как спроектировать архитектуру и реализовать приложение для проверки концепции с помощью технологий разработки Майкрософт (особое внимание уделяется .NET Core) и контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="4aef2-147">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="4aef2-148">Руководство также может оказаться полезным для лиц, принимающих технические решения, например архитекторов корпоративных систем, которым необходимо получить общие сведения об архитектуре и технологиях, прежде чем выбирать подход для создания современных распределенных приложений.</span><span class="sxs-lookup"><span data-stu-id="4aef2-148">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="4aef2-149">Как пользоваться руководством</span><span class="sxs-lookup"><span data-stu-id="4aef2-149">How to use this guide</span></span>

<span data-ttu-id="4aef2-150">В первой части этого руководства приводятся общие сведения о контейнерах Docker, описываются критерии выбора .NET Core или .NET Framework в качестве платформы разработки и дается обзор микрослужб.</span><span class="sxs-lookup"><span data-stu-id="4aef2-150">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="4aef2-151">Это содержимое предназначено для архитекторов и лиц, принимающих технические решения, которым требуется получить общее представление, не вдаваясь в подробности реализации на уровне кода.</span><span class="sxs-lookup"><span data-stu-id="4aef2-151">This content is for architects and technical decision makers who want an overview but don't need to focus on code implementation details.</span></span>

<span data-ttu-id="4aef2-152">Вторая часть руководства начинается с раздела [Процесс разработки для приложений на основе Docker](./docker-application-development-process/index.md).</span><span class="sxs-lookup"><span data-stu-id="4aef2-152">The second part of the guide starts with the [Development process for Docker based applications](./docker-application-development-process/index.md) section.</span></span> <span data-ttu-id="4aef2-153">Он посвящен разработке и шаблонам микрослужб для реализации приложений с помощью .NET Core и Docker.</span><span class="sxs-lookup"><span data-stu-id="4aef2-153">It focuses on development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="4aef2-154">Этот раздел будет особенно интересен разработчикам и архитекторам, которым нужны подробные сведения о реализации на уровне кода и шаблона.</span><span class="sxs-lookup"><span data-stu-id="4aef2-154">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="4aef2-155">Пример приложения на основе микрослужб и контейнеров: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="4aef2-155">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="4aef2-156">Приложение eShopOnContainers — это образец приложения с открытым кодом для .NET Core и микрослужб, который предназначен для развертывания с помощью контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="4aef2-156">The eShopOnContainers application is an open-source reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="4aef2-157">Это приложение состоит из нескольких подсистем, включая ряд пользовательских интерфейсов для электронного магазина (веб-приложения MVC, SPA и собственное мобильное приложение).</span><span class="sxs-lookup"><span data-stu-id="4aef2-157">The application consists of multiple subsystems, including several e-store UI front ends (a Web MVC app, a Web SPA, and a native mobile app).</span></span> <span data-ttu-id="4aef2-158">В его состав также входят внутренние микрослужбы и контейнеры для всех необходимых операций на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="4aef2-158">It also includes the back-end microservices and containers for all required server-side operations.</span></span>

<span data-ttu-id="4aef2-159">Это приложение предназначено для демонстрации архитектурных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4aef2-159">The purpose of the application is to showcase architectural patterns.</span></span> <span data-ttu-id="4aef2-160">**ЭТОТ ШАБЛОН НЕЛЬЗЯ РАССМАТРИВАТЬ КАК ГОТОВУЮ К ЗАПУСКУ ОСНОВУ** для реальных приложений.</span><span class="sxs-lookup"><span data-stu-id="4aef2-160">**IT IS NOT A PRODUCTION-READY TEMPLATE** to start real-world applications.</span></span> <span data-ttu-id="4aef2-161">По сути это приложение постоянно находится в состоянии бета-версии и используется для тестирования новых интересных технологий по мере их появления.</span><span class="sxs-lookup"><span data-stu-id="4aef2-161">In fact, the application is in a permanent beta state, as it’s also used to test new potentially interesting technologies as they show up.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="4aef2-162">Отправьте нам свой отзыв.</span><span class="sxs-lookup"><span data-stu-id="4aef2-162">Send us your feedback!</span></span>

<span data-ttu-id="4aef2-163">Мы создали это руководство, чтобы помочь вам разобраться в архитектуре контейнерных приложений и микрослужб в .NET.</span><span class="sxs-lookup"><span data-stu-id="4aef2-163">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="4aef2-164">Руководство и связанный с ним пример приложения будут развиваться, поэтому мы будем рады вашим отзывам!</span><span class="sxs-lookup"><span data-stu-id="4aef2-164">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="4aef2-165">Если у вас есть замечания касательно того, как можно улучшить этот документ, направляйте их по следующему адресу</span><span class="sxs-lookup"><span data-stu-id="4aef2-165">If you have comments about how this guide can be improved, please send them to:</span></span>

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

## <a name="credits"></a><span data-ttu-id="4aef2-166">Благодарности</span><span class="sxs-lookup"><span data-stu-id="4aef2-166">Credits</span></span>

<span data-ttu-id="4aef2-167">Соавторы:</span><span class="sxs-lookup"><span data-stu-id="4aef2-167">Co-Authors:</span></span>

> <span data-ttu-id="4aef2-168">**Сезар де ла Торре (Cesar de la Torre)** , старший руководитель проекта, команда разработки .NET, корпорация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4aef2-168">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="4aef2-169">**Билл Вэгнер (Bill Wagner)** , старший разработчик содержимого, отдел C+E, корпорация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4aef2-169">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="4aef2-170">**Майк Роусос** (Mike Rousos), главный специалист по разработке программного обеспечения, команда DevDiv CAT, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4aef2-170">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="4aef2-171">Редакторы:</span><span class="sxs-lookup"><span data-stu-id="4aef2-171">Editors:</span></span>

> <span data-ttu-id="4aef2-172">**Майк Поуп** (Mike Pope)</span><span class="sxs-lookup"><span data-stu-id="4aef2-172">**Mike Pope**</span></span>
>
> <span data-ttu-id="4aef2-173">**Стив Хоуг** (Steve Hoag)</span><span class="sxs-lookup"><span data-stu-id="4aef2-173">**Steve Hoag**</span></span>

<span data-ttu-id="4aef2-174">Участники и рецензенты:</span><span class="sxs-lookup"><span data-stu-id="4aef2-174">Participants and reviewers:</span></span>

> <span data-ttu-id="4aef2-175">**Джеффри Рихтер** (Jeffrey Richter), партнер по разработке программного обеспечения, команда Azure, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4aef2-175">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="4aef2-176">**Джимми Богард** (Jimmy Bogard), главный архитектор Headspring</span><span class="sxs-lookup"><span data-stu-id="4aef2-176">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="4aef2-177">**Уди Дахан** (Udi Dahan), основатель и генеральный директор компании Particular Software</span><span class="sxs-lookup"><span data-stu-id="4aef2-177">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="4aef2-178">**Джимми Нилссон** (Jimmy Nilsson), сооснователь и генеральный директор компании Factor10</span><span class="sxs-lookup"><span data-stu-id="4aef2-178">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="4aef2-179">**Гленн Кондрон (Glenn Condron)** , старший менеджер программ, команда ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4aef2-179">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="4aef2-180">**Марк Фасселл** (Mark Fussell), ведущий руководитель проектов, команда Azure Service Fabric, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4aef2-180">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="4aef2-181">**Диего Вега** (Diego Vega), руководитель проектов, команда Entity Framework, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4aef2-181">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="4aef2-182">**Барри Дорранс (Barry Dorrans)** , старший менеджер программ безопасности.</span><span class="sxs-lookup"><span data-stu-id="4aef2-182">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="4aef2-183">**Роуэн Миллер (Rowan Miller)** , старший менеджер программ, Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4aef2-183">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="4aef2-184">**Анкит Астана** (Ankit Asthana), ведущий руководитель проектов, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4aef2-184">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="4aef2-185">**Скотт Хантер** (Scott Hunter), помощник главного руководителя проектов, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4aef2-185">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="4aef2-186">**Ниш Анил (Nish Anil)** , старший менеджер программ, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4aef2-186">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="4aef2-187">**Дилан Райзенбергер** (Dylan Reisenberger), архитектор и руководитель разработки, компания Polly</span><span class="sxs-lookup"><span data-stu-id="4aef2-187">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="4aef2-188">**Стив Смит (Steve Smith)** , преподаватель и разработчик программного обеспечения, [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="4aef2-188">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="4aef2-189">**Ян Купер** (Ian Cooper), архитектор кода, компания Brighter</span><span class="sxs-lookup"><span data-stu-id="4aef2-189">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="4aef2-190">**Унаи Зоррилла** (Unai Zorrilla), архитектор и руководитель разработки, компания Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="4aef2-190">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="4aef2-191">**Эдуард Томас** (Eduard Tomas), руководитель разработки, компания Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="4aef2-191">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="4aef2-192">**Рамон Томас** (Ramon Tomas), разработчик, компания Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="4aef2-192">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="4aef2-193">**Дэвид Санс** (David Sanz), разработчик, компания Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="4aef2-193">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="4aef2-194">**Хавьер Валеро (Javier Valero)** , исполнительный директор Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="4aef2-194">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="4aef2-195">**Пьер Милле (Pierre Millet)** , старший консультант, Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4aef2-195">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="4aef2-196">**Михаэль Фриис** (Michael Friis), менеджер по продукции, компания Docker Inc</span><span class="sxs-lookup"><span data-stu-id="4aef2-196">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="4aef2-197">**Чарльз Лоуэлл** (Charles Lowell), специалист по разработке программного обеспечения, команда VS CAT, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4aef2-197">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>
>
> <span data-ttu-id="4aef2-198">**Мигель Велосо (Miguel Veloso)** , старший консультант Turing Challenge.</span><span class="sxs-lookup"><span data-stu-id="4aef2-198">**Miguel Veloso**, Sr. Consultant at Turing Challenge</span></span>

## <a name="copyright"></a><span data-ttu-id="4aef2-199">Copyright</span><span class="sxs-lookup"><span data-stu-id="4aef2-199">Copyright</span></span>

<span data-ttu-id="4aef2-200">Можно загрузить по ссылке: <https://aka.ms/microservicesebook></span><span class="sxs-lookup"><span data-stu-id="4aef2-200">DOWNLOAD available at: <https://aka.ms/microservicesebook></span></span>

<span data-ttu-id="4aef2-201">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="4aef2-201">PUBLISHED BY</span></span>

<span data-ttu-id="4aef2-202">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4aef2-202">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="4aef2-203">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4aef2-203">A division of Microsoft Corporation</span></span>

<span data-ttu-id="4aef2-204">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="4aef2-204">One Microsoft Way</span></span>

<span data-ttu-id="4aef2-205">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="4aef2-205">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="4aef2-206">© Корпорация Майкрософт (Microsoft Corporation), 2019.</span><span class="sxs-lookup"><span data-stu-id="4aef2-206">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="4aef2-207">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="4aef2-207">All rights reserved.</span></span> <span data-ttu-id="4aef2-208">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="4aef2-208">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="4aef2-209">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="4aef2-209">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="4aef2-210">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="4aef2-210">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="4aef2-211">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="4aef2-211">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="4aef2-212">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="4aef2-212">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="4aef2-213">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте <https://www.microsoft.com>, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4aef2-213">Microsoft and the trademarks listed at <https://www.microsoft.com> on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="4aef2-214">Mac и macOS являются товарными знаками Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="4aef2-214">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="4aef2-215">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="4aef2-215">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="4aef2-216">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="4aef2-216">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="4aef2-217">Вперед</span><span class="sxs-lookup"><span data-stu-id="4aef2-217">Next</span></span>](container-docker-introduction/index.md)
