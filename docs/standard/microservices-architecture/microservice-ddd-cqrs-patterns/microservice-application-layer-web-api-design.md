---
title: "Разработка микрослужбу уровень приложения и веб-API"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Разработка микрослужбу уровень приложения и веб-API"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="25059-104">Разработка микрослужбу уровень приложения и веб-API</span><span class="sxs-lookup"><span data-stu-id="25059-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="25059-105">С помощью СПЛОШНОЙ принципы и внедрения зависимости</span><span class="sxs-lookup"><span data-stu-id="25059-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="25059-106">СПЛОШНОЙ принципы являются критические методы для использования в любой современный и критически важные приложения, например разработка микрослужбу с шаблонами DDD.</span><span class="sxs-lookup"><span data-stu-id="25059-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="25059-107">СПЛОШНОЙ — сокращение от этой группы пять основных принципов:</span><span class="sxs-lookup"><span data-stu-id="25059-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="25059-108">Персональной ответственности</span><span class="sxs-lookup"><span data-stu-id="25059-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="25059-109">Принцип открытый/закрытый</span><span class="sxs-lookup"><span data-stu-id="25059-109">Open/closed principle</span></span>

-   <span data-ttu-id="25059-110">Подстановки Лискоу</span><span class="sxs-lookup"><span data-stu-id="25059-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="25059-111">Разделение принципом инверсии</span><span class="sxs-lookup"><span data-stu-id="25059-111">Inversion Segregation principle</span></span>

-   <span data-ttu-id="25059-112">Принципом инверсии зависимостей</span><span class="sxs-lookup"><span data-stu-id="25059-112">Dependency Inversion principle</span></span>

<span data-ttu-id="25059-113">Сплошная ЛИНИЯ — это больше о способ разработки приложения или внутренней уровней микрослужбу и отделение зависимости между ними.</span><span class="sxs-lookup"><span data-stu-id="25059-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="25059-114">Не относится к домену, но для технической разработки приложения.</span><span class="sxs-lookup"><span data-stu-id="25059-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="25059-115">Окончательный принцип принципом инверсии зависимостей (DI), позволяет отделить уровня инфраструктуры от остальных слоев, позволяет лучше несвязанной реализации DDD слоев.</span><span class="sxs-lookup"><span data-stu-id="25059-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="25059-116">DI — один из способов реализации принципа инверсии зависимостей.</span><span class="sxs-lookup"><span data-stu-id="25059-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="25059-117">Он является методом по достижению слабой связи между объектами и их зависимости.</span><span class="sxs-lookup"><span data-stu-id="25059-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="25059-118">А не непосредственно при создании экземпляра участники совместной работы, или с помощью ссылки на статические, объекты, которые класс должен выполнять свои действия передаваемых (или «внедрены в») класса.</span><span class="sxs-lookup"><span data-stu-id="25059-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="25059-119">Чаще всего классов будет объявлять их зависимости, через своих конструкторов, позволяя следуйте принципу явные зависимости.</span><span class="sxs-lookup"><span data-stu-id="25059-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="25059-120">DI обычно основаны на конкретных контейнеров инверсии управления (IoC).</span><span class="sxs-lookup"><span data-stu-id="25059-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="25059-121">ASP.NET Core предоставляет встроенные простой контейнер IoC, но можно также использовать избранные контейнер IoC, такие как Autofac или Ninject.</span><span class="sxs-lookup"><span data-stu-id="25059-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="25059-122">Следуя СПЛОШНОЙ принципы, ваши классы постепенно естественным образом маленькое, хорошо организованную и легко протестированных.</span><span class="sxs-lookup"><span data-stu-id="25059-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="25059-123">Но как можно вы знаете, если слишком много зависимостей вводится в классах?</span><span class="sxs-lookup"><span data-stu-id="25059-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="25059-124">При использовании DI через конструктор будет определить, просмотрев только количество параметров для ваш конструктор.</span><span class="sxs-lookup"><span data-stu-id="25059-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="25059-125">Если существуют зависимости слишком много, это обычно является признаком ( [кода Запах](http://deviq.com/code-smells/)) класс пытается делать слишком много что, вероятно, нарушил Принцип персональной ответственности.</span><span class="sxs-lookup"><span data-stu-id="25059-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="25059-126">Потребуется другой руководство, чтобы подробно сплошная ЛИНИЯ.</span><span class="sxs-lookup"><span data-stu-id="25059-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="25059-127">Таким образом в этом руководстве требуется наличие только минимальный набор знаний в этих разделах.</span><span class="sxs-lookup"><span data-stu-id="25059-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="25059-128">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="25059-128">Additional resources</span></span>

-   <span data-ttu-id="25059-129">**Сплошная ЛИНИЯ: Принципы объектно-ориентированное Программирование фундаментальных**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="25059-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="25059-130">**Инверсии контейнеры элементов управления и модель внедрения зависимости**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="25059-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="25059-131">**Стив Смит. Новый связующего**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="25059-131">**Steve Smith. New is Glue**
[*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="25059-132">[Предыдущие] (nosql-базы данных сохраняемости infrastructure.md) [Далее] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="25059-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
