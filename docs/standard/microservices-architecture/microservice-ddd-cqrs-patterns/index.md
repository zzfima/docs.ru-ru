---
title: Использование микрослужб с шаблонами DDD и CQRS для решения сложных бизнес-задач
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Использование микрослужб с шаблонами DDD и CQRS для решения сложных бизнес-задач
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/06/2018
ms.openlocfilehash: 1af53f8f37e516219767fdde49eb7da9927d9e29
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2018
ms.locfileid: "50047271"
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

-   **Эрик Эванс (Eric Evans). Domain Language (Предметно-ориентированный язык)**
    [*https://domainlanguage.com/*](https://domainlanguage.com/)

-   **Мартин Фоулер (Martin Fowler). Domain-Driven Design (Предметно-ориентированное проектирование)**
    [*https://martinfowler.com/tags/domain%20driven%20design.html*](https://martinfowler.com/tags/domain%20driven%20design.html)

-   **Джимми Богард (Jimmy Bogard). Strengthening Your Domain: A Primer (Усиление предметной области: учебник для начинающих)**
    [*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)

##### <a name="ddd-books"></a>Книги по DDD

-   **Эрик Эванс (Eric Evans). Предметно-ориентированное проектирование: структуризация сложных программных систем**
    [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Эрик Эванс (Eric Evans). Domain-Driven Design Reference: Definitions and Pattern Summaries (Справочник по предметно-ориентированному проектированию: общие сведения об определениях и шаблонах)**
    [*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)

-   **Вон Вернон (Vaughn Vernon). Реализация предметно-ориентированного проектирования**
    [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **Вон Вернон (Vaughn Vernon). Предметно-ориентированное проектирование. Самое основное**
    [*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)

-   **Джимми Нилссон (Jimmy Nilsson). Применение DDD и шаблонов проектирования**
    [*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)

-   **Сезар де ла Торре (Cesar de la Torre). N-Layered Domain-Oriented Architecture Guide with .NET (Руководство по N-уровневой предметно-ориентированной архитектуре на .NET)**
    [*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)

-   **Абель Аврам (Abel Avram) и Флойд Маринеску (Floyd Marinescu). Domain-Driven Design Quickly (Предметно-ориентированное проектирование: кратко)**
    [*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)

Обучение по DDD

-   **Джули Лерман (Julie Lerman) и Стив Смит (Steve Smith). Domain-Driven Design Fundamentals (Основы предметно-ориентированного проектирования)**
    [*https://bit.ly/PS-DDD*](https://bit.ly/PS-DDD)


>[!div class="step-by-step"]
[Назад](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
[Вперед](apply-simplified-microservice-cqrs-ddd-patterns.md)