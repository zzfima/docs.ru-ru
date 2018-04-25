---
title: Разработка веб-API и уровня приложений для микрослужб
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Разработка веб-API и уровня приложений для микрослужб
keywords: Docker, микрослужбы, ASP.NET, контейнер
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d623a3bc542e0f044d73f405aa639bef0f6d1ec8
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="a8b29-104">Разработка веб-API и уровня приложений для микрослужб</span><span class="sxs-lookup"><span data-stu-id="a8b29-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="a8b29-105">Принципы SOLID и внедрение зависимости</span><span class="sxs-lookup"><span data-stu-id="a8b29-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="a8b29-106">Принципы SOLID являются важными методами, применяемыми в любом современном и критически важном приложении, например при разработке микрослужб при помощи шаблонов проблемно-ориентированного проектирования (DDD).</span><span class="sxs-lookup"><span data-stu-id="a8b29-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="a8b29-107">SOLID — акроним пяти фундаментальных принципов:</span><span class="sxs-lookup"><span data-stu-id="a8b29-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="a8b29-108">Принцип единственной обязанности</span><span class="sxs-lookup"><span data-stu-id="a8b29-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="a8b29-109">Принцип открытия-закрытия</span><span class="sxs-lookup"><span data-stu-id="a8b29-109">Open/closed principle</span></span>

-   <span data-ttu-id="a8b29-110">Принцип подстановки Барбары Лисков</span><span class="sxs-lookup"><span data-stu-id="a8b29-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="a8b29-111">Принцип разделения интерфейса</span><span class="sxs-lookup"><span data-stu-id="a8b29-111">Interface Segregation principle</span></span>

-   <span data-ttu-id="a8b29-112">Принцип инверсии зависимостей</span><span class="sxs-lookup"><span data-stu-id="a8b29-112">Dependency Inversion principle</span></span>

<span data-ttu-id="a8b29-113">Принципы SOLID в большей степени касаются способа разработки приложения или внутренних слоев микрослужб, а также разделения зависимостей между ними.</span><span class="sxs-lookup"><span data-stu-id="a8b29-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="a8b29-114">Они относятся не к домену, а к техническому проектированию приложения.</span><span class="sxs-lookup"><span data-stu-id="a8b29-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="a8b29-115">Последний принцип, принцип инверсии зависимостей (DI), позволяет отделить слой инфраструктуры от остальных слоев, что обеспечивает лучшую несвязанную реализацию слоев DDD.</span><span class="sxs-lookup"><span data-stu-id="a8b29-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="a8b29-116">DI является одним из способов реализации принципа инверсии зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a8b29-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="a8b29-117">Это методика для обеспечения слабой связи между объектами и их зависимостями.</span><span class="sxs-lookup"><span data-stu-id="a8b29-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="a8b29-118">Вместо того, чтобы напрямую создавать экземпляры участников совместной работы или использовать статические ссылки, классу предоставляются (или "внедряются" в него) объекты, необходимые ему для выполнения действий.</span><span class="sxs-lookup"><span data-stu-id="a8b29-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="a8b29-119">Чаще всего классы объявляют зависимости через свой конструктор, позволяя им следовать принципу явных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a8b29-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="a8b29-120">DI обычно основан на особых контейнерах с инверсией управления (IoC).</span><span class="sxs-lookup"><span data-stu-id="a8b29-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="a8b29-121">ASP.NET Core предоставляет простой встроенный контейнер IoC, но можно также использовать любой другой контейнер IoC, такой как Autofac или Ninject.</span><span class="sxs-lookup"><span data-stu-id="a8b29-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="a8b29-122">Соблюдение принципов SOLID поможет сделать ваши классы небольшими, хорошо организованными и удобными в тестировании.</span><span class="sxs-lookup"><span data-stu-id="a8b29-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="a8b29-123">Но как вы узнаете о том, что в ваши классы внедрено слишком много зависимостей?</span><span class="sxs-lookup"><span data-stu-id="a8b29-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="a8b29-124">При использовании DI через конструктор это будет легко определить, посмотрев на количество параметров конструктора.</span><span class="sxs-lookup"><span data-stu-id="a8b29-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="a8b29-125">Большое количество зависимостей обычно указывает ([запахло проблемой](http://deviq.com/code-smells/)) на то, что класс пытается сделать слишком многое и, вероятно, нарушает принцип единственной обязанности.</span><span class="sxs-lookup"><span data-stu-id="a8b29-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="a8b29-126">Для подробного рассмотрения принципов SOLID необходимо отдельное руководство.</span><span class="sxs-lookup"><span data-stu-id="a8b29-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="a8b29-127">Поэтому в этом руководстве требуется наличие только минимальных знаний по этой теме.</span><span class="sxs-lookup"><span data-stu-id="a8b29-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="a8b29-128">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="a8b29-128">Additional resources</span></span>

-   <span data-ttu-id="a8b29-129">**SOLID: фундаментальные принципы ООП**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="a8b29-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="a8b29-130">**Контейнеры инверсии управления и шаблон внедрения зависимостей**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="a8b29-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="a8b29-131">**Стив Смит (Steve Smith). Ключевое слово new**
    [*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="a8b29-131">**Steve Smith. New is Glue**
[*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="a8b29-132">[Назад] (nosql-database-persistence-infrastructure.md) [Далее] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="a8b29-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
