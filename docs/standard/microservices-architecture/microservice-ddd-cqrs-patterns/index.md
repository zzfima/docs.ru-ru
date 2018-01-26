---
title: "Использование микрослужб с шаблонами DDD и CQRS для решения сложных бизнес-задач"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Использование микрослужб с шаблонами DDD и CQRS для решения сложных бизнес-задач"
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
ms.openlocfilehash: 45f29a8d19e49685f864b7ca83e466ceb1f73a62
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="tackling-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a>Использование микрослужб с шаблонами DDD и CQRS для решения сложных бизнес-задач

*Разработка модели предметной области для каждой микрослужбы или ограниченного контекста, который отражает понимание предметной области бизнеса.*

Этот раздел посвящен более сложным микрослужбам, которые реализуются для комплексных подсистем, и микрослужбам, создаваемым на основе знаний экспертов в определенной области с учетом постоянно меняющихся бизнес-правил. Шаблоны архитектуры, используемые в этом разделе, основаны на принципах проблемно-ориентированного проектирования (DDD) и подхода, называемого Command and Query Responsibility Segregation (разделение команд и запросов, CQRS), как показано на рис. 9-1.

![](./media/image1.png)

**Рис. 9-1**. Архитектура внешних микрослужб и внутренние шаблоны архитектуры для каждой микрослужбы

Но большинство методов, применяемых для микрослужб на основе данных, таких как способы реализации службы веб-API ASP.NET Core или предоставления метаданных Swagger с помощью Swashbuckle, также применимы и к более сложным микрослужбам, реализуемым с помощью внутренних шаблонов DDD. Этот раздел дополняет предыдущие, так как большинство описанных ранее методов применимы и в этом случае, а также к любой из микрослужб.

В этом разделе сначала приводятся сведения об упрощенных шаблонах CQRS, используемых в образце приложения eShopOnContainers. Далее вы получите представление о методах DDD, позволяющих найти общие шаблоны, которые можно повторно использовать в приложениях.

DDD — это обширная тема, по которой доступно множество учебных ресурсов. Вы можете начать знакомство с ней с книги [Domain-Driven Design](https://domainlanguage.com/ddd/) (Проблемно-ориентированное проектирование) Эрика Эванса (Eric Evans) и дополнительных материалов от Вона Вернона (Vaughn Vernon), Джимми Нилссона (Jimmy Nilsson), Грега Янга (Greg Young), Уди Дахана (Udi Dahan), Джимми Богарда (Jimmy Bogard) и многих других экспертов по DDD и CQRS. Но учиться применять приемы DDD следует в первую очередь в процессе общения, проведения телеконференций и сеансов моделирования предметных областей с экспертами.

#### <a name="additional-resources"></a>Дополнительные ресурсы

##### <a name="ddd-domain-driven-design"></a>DDD (проблемно-ориентированное проектирование)

-   **Эрик Эванс (Eric Evans). Язык предметной области**
    [*http://domainlanguage.com/*](http://domainlanguage.com/)

-   **Мартин Фоулер (Martin Fowler). Проблемно-ориентированное проектирование**
    [*http://martinfowler.com/tags/domain%20driven%20design.html*](http://martinfowler.com/tags/domain%20driven%20design.html)

-   **Джимми Богард (Jimmy Bogard). Развитие модели предметной области: учебник для начинающих**
    [*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)

##### <a name="ddd-books"></a>Книги по DDD

-   **Эрик Эванс (Eric Evans). Проблемно-ориентированное проектирование: решение сложных задач в программном обеспечении**
    [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Эрик Эванс (Eric Evans). Справочник по проблемно-ориентированному проектированию: определения и сводки по шаблонам**
    [*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)

-   **Вон Вернон (Vaughn Vernon). Реализация проблемно-ориентированного проектирования**
    [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **Вон Вернон (Vaughn Vernon). Основы проблемно-ориентированного проектирования**
    [*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)

-   **Джимми Нилссон (Jimmy Nilsson). Применение проблемно-ориентированного проектирования и шаблонов**
    [*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)

-   **Сезар де ла Торре (Cesar de la Torre). Руководство по N-уровневой проблемно-ориентированной архитектуре на основе .NET**
    [*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)

-   **Абель Аврам (Abel Avram) и Флойд Маринеску (Floyd Marinescu). Коротко о проблемно-ориентированном проектировании**
    [*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)

Обучение по DDD

-   **Джули Лерман (Julie Lerman) и Стив Смит (Steve Smith). Основы проблемно-ориентированного проектирования**
    [*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)


>[!div class="step-by-step"]
[Назад] (../multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md) [Далее] (apply-simplified-microservice-cqrs-ddd-patterns.md)
