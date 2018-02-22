---
title: "Архитектура микрослужб"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Архитектура микрослужб"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 453f8a22157eee9601f2586d49d872d90634bb61
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="microservices-architecture"></a><span data-ttu-id="e13da-104">Архитектура микрослужб</span><span class="sxs-lookup"><span data-stu-id="e13da-104">Microservices architecture</span></span>

<span data-ttu-id="e13da-105">Само название предполагает, что архитектура микрослужб является подходом к созданию серверного приложения как набора малых служб,</span><span class="sxs-lookup"><span data-stu-id="e13da-105">As the name implies, a microservices architecture is an approach to building a server application as a set of small services.</span></span> <span data-ttu-id="e13da-106">где каждая служба выполняется в своем процессе и взаимодействует с остальными службами по таким протоколам, как HTTP/HTTPS, WebSockets или [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).</span><span class="sxs-lookup"><span data-stu-id="e13da-106">Each service runs in its own process and communicates with other processes using protocols such as HTTP/HTTPS, WebSockets, or [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).</span></span> <span data-ttu-id="e13da-107">Каждая микрослужба реализует специфические возможности в предметной области и свою бизнес-логику в рамках определенного ограниченного контекста, должна разрабатываться автономно и развертываться независимо.</span><span class="sxs-lookup"><span data-stu-id="e13da-107">Each microservice implements a specific end-to-end domain or business capability within a certain context boundary, and each must be developed autonomously and be deployable independently.</span></span> <span data-ttu-id="e13da-108">Наконец, у каждой микрослужбы должны быть соответствующие собственные модель данных и логика предметной области (владение и децентрализованное управление данными); для каждой микрослужбы можно применять разные технологии хранилищ (SQL, NoSQL) и разные языки программирования.</span><span class="sxs-lookup"><span data-stu-id="e13da-108">Finally, each microservice should own its related domain data model and domain logic (sovereignty and decentralized data management) based on different data storage technologies (SQL, NoSQL) and different programming languages.</span></span>

<span data-ttu-id="e13da-109">Каково размера должна быть микрослужба?</span><span class="sxs-lookup"><span data-stu-id="e13da-109">What size should a microservice be?</span></span> <span data-ttu-id="e13da-110">При разработке микрослужбы размер не должен быть важным фактором.</span><span class="sxs-lookup"><span data-stu-id="e13da-110">When developing a microservice, size should not be the important point.</span></span> <span data-ttu-id="e13da-111">Главным должно быть создание слабо связанных служб, что позволяет добавиться автономности при разработке, развертывании и масштабировании каждой службы.</span><span class="sxs-lookup"><span data-stu-id="e13da-111">Instead, the important point should be to create loosely coupled services so you have autonomy of development, deployment, and scale, for each service.</span></span> <span data-ttu-id="e13da-112">Конечно же, при определении и проектировании микрослужб следует стремиться к тому, чтобы они были как можно меньше, если только они не имеют слишком много прямых зависимостей от других микрослужб.</span><span class="sxs-lookup"><span data-stu-id="e13da-112">Of course, when identifying and designing microservices, you should try to make them as small as possible as long as you do not have too many direct dependencies with other microservices.</span></span> <span data-ttu-id="e13da-113">Внутренняя связанность микрослужбы и ее независимость от других служб важнее ее размера.</span><span class="sxs-lookup"><span data-stu-id="e13da-113">More important than the size of the microservice is the internal cohesion it must have and its independence from other services.</span></span>

<span data-ttu-id="e13da-114">Почему следует использовать архитектуру микрослужб?</span><span class="sxs-lookup"><span data-stu-id="e13da-114">Why a microservices architecture?</span></span> <span data-ttu-id="e13da-115">Если говорить кратко, то это гибкость в долгосрочной перспективе.</span><span class="sxs-lookup"><span data-stu-id="e13da-115">In short, it provides long-term agility.</span></span> <span data-ttu-id="e13da-116">Микрослужбы обеспечивают превосходные возможности сопровождения в крупных комплексных системах с высокой масштабируемостью за счет создания приложений, основанных на множестве независимо развертываемых служб с автономными жизненными циклами.</span><span class="sxs-lookup"><span data-stu-id="e13da-116">Microservices enable better maintainability in complex, large, and highly-scalable systems by letting you create applications based on many independently deployable services that each have granular and autonomous lifecycles.</span></span>

<span data-ttu-id="e13da-117">Дополнительное преимущество в том, что микрослужбы можно масштабировать независимо.</span><span class="sxs-lookup"><span data-stu-id="e13da-117">As an additional benefit, microservices can scale out independently.</span></span> <span data-ttu-id="e13da-118">Вместо монолитного приложения, которое нужно масштабировать как единое целое, вы масштабируете отдельные микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="e13da-118">Instead of having a single monolithic application that you must scale out as a unit, you can instead scale out specific microservices.</span></span> <span data-ttu-id="e13da-119">Тем самым можно масштабировать только функциональную область, требующую больше вычислительных или сетевых ресурсов, не затрагивая другие области приложения, которые на самом деле не нуждаются в масштабировании.</span><span class="sxs-lookup"><span data-stu-id="e13da-119">That way, you can scale just the functional area that needs more processing power or network bandwidth to support demand, rather than scaling out other areas of the application that do not need to be scaled.</span></span> <span data-ttu-id="e13da-120">Таким образом можно сократить расходы, так как требуется меньше оборудования.</span><span class="sxs-lookup"><span data-stu-id="e13da-120">That means cost savings because you need less hardware.</span></span>

![](./media/image6.png)

<span data-ttu-id="e13da-121">**Рис. 4-6**.</span><span class="sxs-lookup"><span data-stu-id="e13da-121">**Figure 4-6**.</span></span> <span data-ttu-id="e13da-122">Монолитное развертывание в сравнении с подходом на основе микрослужб</span><span class="sxs-lookup"><span data-stu-id="e13da-122">Monolithic deployment versus the microservices approach</span></span>

<span data-ttu-id="e13da-123">Как показано на рис. 4-6, подход на основе микрослужб нацелен на гибкость изменений и ускорение последовательных улучшений каждой микрослужбы, поскольку вы получаете возможность изменять небольшие части крупных, комплексных и масштабируемых приложений.</span><span class="sxs-lookup"><span data-stu-id="e13da-123">As Figure 4-6 shows, the microservices approach allows agile changes and rapid iteration of each microservice, because you can change specific, small areas of complex, large, and scalable applications.</span></span>

<span data-ttu-id="e13da-124">Архитектура приложений на основе микрослужб позволяет применять принципы непрерывной интеграции и поставки.</span><span class="sxs-lookup"><span data-stu-id="e13da-124">Architecting fine-grained microservices-based applications enables continuous integration and continuous delivery practices.</span></span> <span data-ttu-id="e13da-125">Она ускоряет доставку новых функций в приложение.</span><span class="sxs-lookup"><span data-stu-id="e13da-125">It also accelerates delivery of new functions into the application.</span></span> <span data-ttu-id="e13da-126">Кроме того, разделение приложений на небольшие компоненты позволяет запускать и тестировать микрослужбы изолированно, а также развивать их независимо друг от друга, в то же время соблюдая строгие контракты их взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e13da-126">Fine-grained composition of applications also allows you to run and test microservices in isolation, and to evolve them autonomously while maintaining clear contracts between them.</span></span> <span data-ttu-id="e13da-127">Пока контракты или интерфейсы не нарушаются, можно изменять внутреннюю реализацию любой микрослужбы и добавлять новую функциональность, не мешая работе других микрослужб.</span><span class="sxs-lookup"><span data-stu-id="e13da-127">As long as you do not change the interfaces or contracts, you can change the internal implementation of any microservice or add new functionality without breaking other microservices.</span></span>

<span data-ttu-id="e13da-128">Ниже перечислены важные аспекты успешного ввода системы на основе микрослужб в эксплуатацию:</span><span class="sxs-lookup"><span data-stu-id="e13da-128">The following are important aspects to enable success in going into production with a microservices-based system:</span></span>

-   <span data-ttu-id="e13da-129">мониторинг и проверки работоспособности служб и инфраструктуры;</span><span class="sxs-lookup"><span data-stu-id="e13da-129">Monitoring and health checks of the services and infrastructure.</span></span>

-   <span data-ttu-id="e13da-130">масштабируемая инфраструктура служб (то есть облако и оркестраторы);</span><span class="sxs-lookup"><span data-stu-id="e13da-130">Scalable infrastructure for the services (that is, cloud and orchestrators).</span></span>

-   <span data-ttu-id="e13da-131">проектирование и реализация безопасности на разных уровнях: проверка подлинности, авторизация, управление секретами, безопасный обмен данными и т. д.;</span><span class="sxs-lookup"><span data-stu-id="e13da-131">Security design and implementation at multiple levels: authentication, authorization, secrets management, secure communication, etc.</span></span>

-   <span data-ttu-id="e13da-132">быстрая поставка приложения, причем разными микрослужбами обычно занимаются разные команды;</span><span class="sxs-lookup"><span data-stu-id="e13da-132">Rapid application delivery, usually with different teams focusing on different microservices.</span></span>

-   <span data-ttu-id="e13da-133">методики и инфраструктура DevOps и непрерывной интеграции и поставки.</span><span class="sxs-lookup"><span data-stu-id="e13da-133">DevOps and CI/CD practices and infrastructure.</span></span>

<span data-ttu-id="e13da-134">Из этих аспектов только первые три рассматриваются в данном руководстве.</span><span class="sxs-lookup"><span data-stu-id="e13da-134">Of these, only the first three are covered or introduced in this guide.</span></span> <span data-ttu-id="e13da-135">Последние два, связанные с жизненным циклом приложения, описываются в дополнительной электронной книге [Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт](https://aka.ms/dockerlifecycleebook).</span><span class="sxs-lookup"><span data-stu-id="e13da-135">The last two points, which are related to application lifecycle, are covered in the additional [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) e-book.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e13da-136">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e13da-136">Additional resources</span></span>

-   <span data-ttu-id="e13da-137">**Марк Руссинович (Mark Russinovich). Микрослужбы: революция в сфере приложений, движимая облачными технологиями**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span><span class="sxs-lookup"><span data-stu-id="e13da-137">**Mark Russinovich. Microservices: An application revolution powered by the cloud**
[*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span></span>

-   <span data-ttu-id="e13da-138">**Мартин Фоулер (Martin Fowler). Микрослужбы**
    [*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)</span><span class="sxs-lookup"><span data-stu-id="e13da-138">**Martin Fowler. Microservices**
[*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)</span></span>

-   <span data-ttu-id="e13da-139">**Мартин Фоулер (Martin Fowler). Требования для микрослужб**
    [*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)</span><span class="sxs-lookup"><span data-stu-id="e13da-139">**Martin Fowler. Microservice Prerequisites**
[*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)</span></span>

-   <span data-ttu-id="e13da-140">**Джимми Нилссон (Jimmy Nilsson). Фрагментирование облачных вычислений**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span><span class="sxs-lookup"><span data-stu-id="e13da-140">**Jimmy Nilsson. Chunk Cloud Computing**
[*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span></span>

-   <span data-ttu-id="e13da-141">**Сезар де ла Торре (Cesar de la Torre). Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт** (электронная книга, доступная для скачивания) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span><span class="sxs-lookup"><span data-stu-id="e13da-141">**Cesar de la Torre. Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="e13da-142">[Назад] (service-oriented-architecture.md) [Далее] (data-sovereignty-per-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="e13da-142">[Previous] (service-oriented-architecture.md) [Next] (data-sovereignty-per-microservice.md)</span></span>
