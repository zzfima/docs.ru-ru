---
title: Использование микрослужб с шаблонами DDD и CQRS для решения сложных бизнес-задач
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Сведения об использовании микрослужб с шаблонами DDD и CQRS для решения сложных бизнес-задач
ms.date: 10/08/2018
ms.openlocfilehash: 88b105b68307c8587f877bb9ddf370e143d8539b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "73739828"
---
# <a name="tackle-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a>Использование микрослужб с шаблонами DDD и CQRS для решения сложных бизнес-задач

*Разработка модели предметной области для каждой микрослужбы или ограниченного контекста, который отражает понимание предметной области бизнеса.*

Этот раздел посвящен более сложным микрослужбам, которые реализуются для комплексных подсистем, и микрослужбам, создаваемым на основе знаний экспертов в определенной области с учетом постоянно меняющихся бизнес-правил. Шаблоны архитектуры, используемые в этом разделе, основаны на принципах проблемно-ориентированного проектирования (DDD) и разделения команд и запросов (CQRS), как показано на рис. 7-1.

:::image type="complex" source="./media/index/internal-versus-external-architecture.png" alt-text="Схема сравнения шаблонов внешней и внутренней архитектуры.":::
Внешняя архитектура: шаблоны микрослужб, шлюзы API, устойчивый обмен данными, публикации и подписки и т.д. Внутривенная архитектура: управление данными, CRUD, шаблоны DDD, внедрение зависимостей, несколько библиотек и т.д.
:::image-end:::

**Рис. 7-1**. Архитектура внешних микрослужб и внутренние шаблоны архитектуры для каждой микрослужбы

Но большинство методов, применяемых для микрослужб на основе данных, таких как способы реализации службы веб-API ASP.NET Core или предоставления метаданных Swagger с помощью Swashbuckle или NSwag, также применимы и к более сложным микрослужбам, реализуемым с помощью внутренних шаблонов DDD. Этот раздел дополняет предыдущие, так как большинство описанных ранее методов применимы и в этом случае, а также к любой из микрослужб.

В этом разделе сначала приводятся сведения об упрощенных шаблонах CQRS, используемых в образце приложения eShopOnContainers. Далее вы получите представление о методах DDD, позволяющих найти общие шаблоны, которые можно повторно использовать в приложениях.

DDD — это обширная тема, по которой доступно множество учебных ресурсов. Вы можете начать знакомство с ней с книги [Domain-Driven Design](https://domainlanguage.com/ddd/) (Проблемно-ориентированное проектирование) Эрика Эванса (Eric Evans) и дополнительных материалов от Вона Вернона (Vaughn Vernon), Джимми Нилссона (Jimmy Nilsson), Грега Янга (Greg Young), Уди Дахана (Udi Dahan), Джимми Богарда (Jimmy Bogard) и многих других экспертов по DDD и CQRS. Но учиться применять приемы DDD следует в первую очередь в процессе общения, проведения телеконференций и сеансов моделирования предметных областей с экспертами.

#### <a name="additional-resources"></a>Дополнительные ресурсы

##### <a name="ddd-domain-driven-design"></a>DDD (проблемно-ориентированное проектирование)

- **Эрик Эванс (Eric Evans). Предметно-ориентированный язык**  \
  <https://domainlanguage.com/>

- **Мартин Фоулер (Martin Fowler). Предметно-ориентированное проектирование** \
  <https://martinfowler.com/tags/domain%20driven%20design.html>

- **Джимми Богард (Jimmy Bogard). Усиление предметной области: руководство для начинающих** \
  <https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/>

##### <a name="ddd-books"></a>Книги по DDD

- **Эрик Эванс (Eric Evans). Domain-Driven Design: Tackling Complexity in the Heart of Software (Предметно-ориентированное проектирование. Структуризация сложных программных систем)**  \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- **Эрик Эванс (Eric Evans). Справочник по предметно-ориентированному проектированию: Определения и обзор шаблонов** \
  <https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/>

- **Вон Вернон (Vaughn Vernon). Реализация проблемно-ориентированного проектирования** \
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- **Вон Вернон (Vaughn Vernon). Основные сведения о предметно-ориентированном проектировании** \
  <https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/>

- **Джимми Нилссон (Jimmy Nilsson). Применение предметно-ориентированного проектирования и шаблонов** \
  <https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/>

- **Сезар де ла Торре (Cesar de la Torre). Руководство по N-уровневой предметно-ориентированной архитектуре на .NET** \
  <https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/>

- **Абель Аврам (Abel Avram) и Флойд Маринеску (Floyd Marinescu). Кратко о предметно-ориентированном проектировании** \
  <https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/>

- **Скотт Миллетт (Scott Millett), Ник Тюн (Nick Tune). Шаблоны, принципы и методы предметно-ориентированного проектирования** \
  <http://www.wrox.com/WileyCDA/WroxTitle/Patterns-Principles-and-Practices-of-Domain-Driven-Design.productCd-1118714709.html>

##### <a name="ddd-training"></a>Обучение по DDD

- **Джули Лерман (Julie Lerman) и Стив Смит (Steve Smith). Основы предметно-ориентированного проектирования** \
  <https://bit.ly/PS-DDD>

>[!div class="step-by-step"]
>[Назад](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
>[Вперед](apply-simplified-microservice-cqrs-ddd-patterns.md)
