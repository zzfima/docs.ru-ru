---
title: Создание, развитие и управление версиями API-интерфейсов и контрактов микрослужб
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Создание, развитие и управление версиями API-интерфейсов и контрактов микрослужб
keywords: Docker, микрослужбы, ASP.NET, контейнер
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7a80405f0a206cfaa0462392eddfc95878353cd7
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a><span data-ttu-id="25ecb-104">Создание, развитие и управление версиями API-интерфейсов и контрактов микрослужб</span><span class="sxs-lookup"><span data-stu-id="25ecb-104">Creating, evolving, and versioning microservice APIs and contracts</span></span>

<span data-ttu-id="25ecb-105">API микрослужбы представляет собой контракт между службой и ее клиентами.</span><span class="sxs-lookup"><span data-stu-id="25ecb-105">A microservice API is a contract between the service and its clients.</span></span> <span data-ttu-id="25ecb-106">Вы сможете развивать микрослужбу независимо только в том случае, если не нарушаете ее контракт API; вот почему контракт так важен.</span><span class="sxs-lookup"><span data-stu-id="25ecb-106">You will be able to evolve a microservice independently only if you do not break its API contract, which is why the contract is so important.</span></span> <span data-ttu-id="25ecb-107">Если изменить контракт, это повлияет на клиентские приложения или на шлюз API.</span><span class="sxs-lookup"><span data-stu-id="25ecb-107">If you change the contract, it will impact your client applications or your API Gateway.</span></span>

<span data-ttu-id="25ecb-108">Характер определения API зависит от того, какой протокол используется.</span><span class="sxs-lookup"><span data-stu-id="25ecb-108">The nature of the API definition depends on which protocol you are using.</span></span> <span data-ttu-id="25ecb-109">Например, при использовании обмена сообщениями (такого как [AMQP](https://www.amqp.org/)) API состоит из типов сообщений.</span><span class="sxs-lookup"><span data-stu-id="25ecb-109">For instance, if you are using messaging (like [AMQP](https://www.amqp.org/)), the API consists of the message types.</span></span> <span data-ttu-id="25ecb-110">При использовании HTTP и службы RESTful API состоит из URL-адресов и форматов JSON запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="25ecb-110">If you are using HTTP and RESTful services, the API consists of the URLs and the request and response JSON formats.</span></span>

<span data-ttu-id="25ecb-111">Тем не менее, даже если вы внимательно относитесь к первоначальному контракту, со временем API службы потребуется изменить.</span><span class="sxs-lookup"><span data-stu-id="25ecb-111">However, even if you are thoughtful about your initial contract, a service API will need to change over time.</span></span> <span data-ttu-id="25ecb-112">Когда это происходит, и особенно в том случае, если ваш API является общим API, используемым несколькими клиентскими приложениями, как правило, вы не можете заставить всех клиентов обновиться до вашего нового контракта API.</span><span class="sxs-lookup"><span data-stu-id="25ecb-112">When that happens—and especially if your API is a public API consumed by multiple client applications—you typically cannot force all clients to upgrade to your new API contract.</span></span> <span data-ttu-id="25ecb-113">Обычно требуется последовательное развертывание новых версий службы таким образом, чтобы и старая, и новая версии контракта службы работали одновременно.</span><span class="sxs-lookup"><span data-stu-id="25ecb-113">You usually need to incrementally deploy new versions of a service in a way that both old and new versions of a service contract are running simultaneously.</span></span> <span data-ttu-id="25ecb-114">Следовательно, важно иметь стратегию для управления версиями вашей службы.</span><span class="sxs-lookup"><span data-stu-id="25ecb-114">Therefore, it is important to have a strategy for your service versioning.</span></span>

<span data-ttu-id="25ecb-115">Если изменения API невелики, например, вы добавили в API атрибуты или параметры, то клиенты, использующие старый API, должны переключиться на новую версию службы и работать с ней.</span><span class="sxs-lookup"><span data-stu-id="25ecb-115">When the API changes are small, like if you add attributes or parameters to your API, clients that use an older API should switch and work with the new version of the service.</span></span> <span data-ttu-id="25ecb-116">Вы могли бы предоставить значения по умолчанию для каких-либо отсутствующих, но необходимых атрибутов, а клиенты могли бы игнорировать любые лишние атрибуты ответа.</span><span class="sxs-lookup"><span data-stu-id="25ecb-116">You might be able to provide default values for any missing attributes that are required, and the clients might be able to ignore any extra response attributes.</span></span>

<span data-ttu-id="25ecb-117">Однако иногда требуется внести в API службы важные и несовместимые изменения.</span><span class="sxs-lookup"><span data-stu-id="25ecb-117">However, sometimes you need to make major and incompatible changes to a service API.</span></span> <span data-ttu-id="25ecb-118">Поскольку вы не сможете обеспечить принудительное немедленное обновление клиентских приложений или служб до новой версии, служба должна некоторое время поддерживать старые версии API.</span><span class="sxs-lookup"><span data-stu-id="25ecb-118">Because you might not be able to force client applications or services to upgrade immediately to the new version, a service must support older versions of the API for some period.</span></span> <span data-ttu-id="25ecb-119">Если используется механизм на основе HTTP, такой как REST, один из подходов заключается во внедрении номера версии API в URL-адрес или в заголовок HTTP.</span><span class="sxs-lookup"><span data-stu-id="25ecb-119">If you are using an HTTP-based mechanism such as REST, one approach is to embed the API version number in the URL or into a HTTP header.</span></span> <span data-ttu-id="25ecb-120">Затем можно либо одновременно реализовать обе версии службы в одном и том же экземпляре службы, либо развернуть разные экземпляры, каждый из которых обрабатывает версию API.</span><span class="sxs-lookup"><span data-stu-id="25ecb-120">Then you can decide between implementing both versions of the service simultaneously within the same service instance, or deploying different instances that each handle a version of the API.</span></span> <span data-ttu-id="25ecb-121">Для разделения разных версий реализации по независимым обработчикам рекомендуется использовать [шаблон Mediator](https://en.wikipedia.org/wiki/Mediator_pattern) (например, [библиотеку MediatR](https://github.com/jbogard/MediatR)).</span><span class="sxs-lookup"><span data-stu-id="25ecb-121">A good approach for this is the [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern) (for example, [MediatR library](https://github.com/jbogard/MediatR)) to decouple the different implementation versions into independent handlers.</span></span>

<span data-ttu-id="25ecb-122">Наконец, при использовании архитектуры REST лучшим решением для управления версиями служб и разрешения развиваемых API является использование [гиперсредств](https://www.infoq.com/articles/mark-baker-hypermedia).</span><span class="sxs-lookup"><span data-stu-id="25ecb-122">Finally, if you are using a REST architecture, [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) is the best solution for versioning your services and allowing evolvable APIs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25ecb-123">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="25ecb-123">Additional resources</span></span>

-   <span data-ttu-id="25ecb-124">**Скотт Ханселман (Scott Hanselman). Упрощение управления версиями веб-API ASP.NET Core с поддержкой REST**
    <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx></span><span class="sxs-lookup"><span data-stu-id="25ecb-124">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
<https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx></span></span>

-   <span data-ttu-id="25ecb-125">**Управление версиями веб-API с поддержкой REST**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span><span class="sxs-lookup"><span data-stu-id="25ecb-125">**Versioning a RESTful web API**
[*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span></span>

-   <span data-ttu-id="25ecb-126">**Рой Филдинг (Roy Fielding). Управление версиями, гипермедиа и REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning></span><span class="sxs-lookup"><span data-stu-id="25ecb-126">**Roy Fielding. Versioning, Hypermedia, and REST**
<https://www.infoq.com/articles/roy-fielding-on-versioning></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="25ecb-127">[Назад] (asynchronous-message-based-communication.md) [Далее] (microservices-addressability-service-registry.md)</span><span class="sxs-lookup"><span data-stu-id="25ecb-127">[Previous] (asynchronous-message-based-communication.md) [Next] (microservices-addressability-service-registry.md)</span></span>
