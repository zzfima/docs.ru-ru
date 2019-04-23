---
title: Разработка веб-API и уровня приложений для микрослужб
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Краткое описание принципов SOLID для проектирования уровня приложений.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/08/2018
ms.openlocfilehash: 9177ac9a79afaea01f0ec21b0a64bad5a94e9966
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612242"
---
# <a name="design-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="5fb60-103">Разработка веб-API и уровня приложений для микрослужб</span><span class="sxs-lookup"><span data-stu-id="5fb60-103">Design the microservice application layer and Web API</span></span>

## <a name="use-solid-principles-and-dependency-injection"></a><span data-ttu-id="5fb60-104">Принципы SOLID и внедрение зависимостей</span><span class="sxs-lookup"><span data-stu-id="5fb60-104">Use SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="5fb60-105">Принципы SOLID являются важными методами, применяемыми в любом современном и критически важном приложении, например при разработке микрослужб при помощи шаблонов проблемно-ориентированного проектирования (DDD).</span><span class="sxs-lookup"><span data-stu-id="5fb60-105">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="5fb60-106">SOLID — акроним пяти фундаментальных принципов:</span><span class="sxs-lookup"><span data-stu-id="5fb60-106">SOLID is an acronym that groups five fundamental principles:</span></span>

- <span data-ttu-id="5fb60-107">Принцип единственной обязанности</span><span class="sxs-lookup"><span data-stu-id="5fb60-107">Single Responsibility principle</span></span>

- <span data-ttu-id="5fb60-108">Принцип открытия-закрытия</span><span class="sxs-lookup"><span data-stu-id="5fb60-108">Open/closed principle</span></span>

- <span data-ttu-id="5fb60-109">Принцип подстановки Барбары Лисков</span><span class="sxs-lookup"><span data-stu-id="5fb60-109">Liskov substitution principle</span></span>

- <span data-ttu-id="5fb60-110">Принцип разделения интерфейса</span><span class="sxs-lookup"><span data-stu-id="5fb60-110">Interface Segregation principle</span></span>

- <span data-ttu-id="5fb60-111">Принцип инверсии зависимостей</span><span class="sxs-lookup"><span data-stu-id="5fb60-111">Dependency Inversion principle</span></span>

<span data-ttu-id="5fb60-112">Принципы SOLID в большей степени касаются способа разработки приложения или внутренних слоев микрослужб, а также разделения зависимостей между ними.</span><span class="sxs-lookup"><span data-stu-id="5fb60-112">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="5fb60-113">Они относятся не к домену, а к техническому проектированию приложения.</span><span class="sxs-lookup"><span data-stu-id="5fb60-113">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="5fb60-114">Последний принцип, принцип инверсии зависимостей (DI), позволяет отделить слой инфраструктуры от остальных слоев, что обеспечивает лучшую несвязанную реализацию слоев DDD.</span><span class="sxs-lookup"><span data-stu-id="5fb60-114">The final principle, the Dependency Inversion principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="5fb60-115">Внедрение зависимостей — это один из способов реализации принципа инверсии зависимостей.</span><span class="sxs-lookup"><span data-stu-id="5fb60-115">Dependency Injection (DI) is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="5fb60-116">Это методика для обеспечения слабой связи между объектами и их зависимостями.</span><span class="sxs-lookup"><span data-stu-id="5fb60-116">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="5fb60-117">Вместо того, чтобы напрямую создавать экземпляры участников совместной работы или использовать статические ссылки (например, использовать new…), классу предоставляются (или "внедряются" в него) объекты, необходимые ему для выполнения действий.</span><span class="sxs-lookup"><span data-stu-id="5fb60-117">Rather than directly instantiating collaborators, or using static references (that is, using new…), the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="5fb60-118">Чаще всего классы объявляют зависимости через свой конструктор, позволяя им следовать принципу явных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="5fb60-118">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="5fb60-119">Внедрение зависимостей обычно основано на особых контейнерах с инверсией управления (IoC).</span><span class="sxs-lookup"><span data-stu-id="5fb60-119">Dependency Injection is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="5fb60-120">ASP.NET Core предоставляет простой встроенный контейнер IoC, но можно также использовать любой другой контейнер IoC, такой как Autofac или Ninject.</span><span class="sxs-lookup"><span data-stu-id="5fb60-120">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="5fb60-121">Соблюдение принципов SOLID поможет сделать ваши классы небольшими, хорошо организованными и удобными в тестировании.</span><span class="sxs-lookup"><span data-stu-id="5fb60-121">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="5fb60-122">Но как вы узнаете о том, что в ваши классы внедрено слишком много зависимостей?</span><span class="sxs-lookup"><span data-stu-id="5fb60-122">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="5fb60-123">При использовании DI через конструктор это будет легко определить, посмотрев на количество параметров конструктора.</span><span class="sxs-lookup"><span data-stu-id="5fb60-123">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="5fb60-124">Большое количество зависимостей обычно указывает ([запахло проблемой](https://deviq.com/code-smells/)) на то, что класс пытается сделать слишком многое и, вероятно, нарушает принцип единственной обязанности.</span><span class="sxs-lookup"><span data-stu-id="5fb60-124">If there are too many dependencies, this is generally a sign (a [code smell](https://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="5fb60-125">Для подробного рассмотрения принципов SOLID необходимо отдельное руководство.</span><span class="sxs-lookup"><span data-stu-id="5fb60-125">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="5fb60-126">Поэтому в этом руководстве требуется наличие только минимальных знаний по этой теме.</span><span class="sxs-lookup"><span data-stu-id="5fb60-126">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="5fb60-127">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="5fb60-127">Additional resources</span></span>

- <span data-ttu-id="5fb60-128">**SOLID: базовые принципы ООП** \\</span><span class="sxs-lookup"><span data-stu-id="5fb60-128">**SOLID: Fundamental OOP Principles** \\</span></span>
  <https://deviq.com/solid/>

- <span data-ttu-id="5fb60-129">**Контейнеры с инверсией управления и шаблон внедрения зависимостей** \\</span><span class="sxs-lookup"><span data-stu-id="5fb60-129">**Inversion of Control Containers and the Dependency Injection pattern** \\</span></span>
  <https://martinfowler.com/articles/injection.html>

- <span data-ttu-id="5fb60-130">**Стив Смит (Steve Smith). Ключевое слово new** \\</span><span class="sxs-lookup"><span data-stu-id="5fb60-130">**Steve Smith. New is Glue** \\</span></span>
  <https://ardalis.com/new-is-glue>

> [!div class="step-by-step"]
> <span data-ttu-id="5fb60-131">[Назад](nosql-database-persistence-infrastructure.md)
> [Вперед](microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="5fb60-131">[Previous](nosql-database-persistence-infrastructure.md)
[Next](microservice-application-layer-implementation-web-api.md)</span></span>
