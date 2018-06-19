---
title: Микрослужбы .NET. Архитектура контейнерных приложений .NET
description: 'Микрослужбы .NET: архитектура контейнерных приложений .NET | Микрослужбы — это модульные службы, развертываемые независимо друг от друга. Контейнеры Docker (для Linux и Windows) упрощают развертывание и тестирование путем объединения службы и ее зависимостей в единый модуль, запускаемый в изолированной среде.'
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/06/2018
ms.openlocfilehash: 58bb915c825cd69c68b3955573145ae6a1b1a6e4
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231425"
---
![](./media/cover.png)

# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="00d6a-105">Микрослужбы .NET.</span><span class="sxs-lookup"><span data-stu-id="00d6a-105">.NET Microservices.</span></span> <span data-ttu-id="00d6a-106">Архитектура контейнерных приложений .NET</span><span class="sxs-lookup"><span data-stu-id="00d6a-106">Architecture for Containerized .NET Applications</span></span>

<span data-ttu-id="00d6a-107">Можно загрузить по ссылке: <https://aka.ms/microservicesebook></span><span class="sxs-lookup"><span data-stu-id="00d6a-107">DOWNLOAD available at: <https://aka.ms/microservicesebook></span></span>

<span data-ttu-id="00d6a-108">ИЗДАТЕЛЬ</span><span class="sxs-lookup"><span data-stu-id="00d6a-108">PUBLISHED BY</span></span>

<span data-ttu-id="00d6a-109">Подразделение Microsoft Developer Division, команды разработки .NET и Visual Studio</span><span class="sxs-lookup"><span data-stu-id="00d6a-109">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="00d6a-110">Подразделение корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-110">A division of Microsoft Corporation</span></span>

<span data-ttu-id="00d6a-111">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="00d6a-111">One Microsoft Way</span></span>

<span data-ttu-id="00d6a-112">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="00d6a-112">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="00d6a-113">© Корпорация Майкрософт (Microsoft Corporation), 2018.</span><span class="sxs-lookup"><span data-stu-id="00d6a-113">Copyright © 2018 by Microsoft Corporation</span></span>

<span data-ttu-id="00d6a-114">Все права защищены.</span><span class="sxs-lookup"><span data-stu-id="00d6a-114">All rights reserved.</span></span> <span data-ttu-id="00d6a-115">Запрещается полное или частичное воспроизведение или передача настоящей книги в любом виде или любыми средствами без письменного разрешения издателя.</span><span class="sxs-lookup"><span data-stu-id="00d6a-115">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="00d6a-116">Эта книга предоставляется на условиях "как есть" и выражает взгляды и мнения автора.</span><span class="sxs-lookup"><span data-stu-id="00d6a-116">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="00d6a-117">Взгляды, мнения и сведения, содержащиеся в этой книге, включая URL-адреса и другие ссылки на веб-сайты, могут изменяться без уведомления.</span><span class="sxs-lookup"><span data-stu-id="00d6a-117">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="00d6a-118">Некоторые приведенные в книге примеры служат только для иллюстрации и являются вымышленными.</span><span class="sxs-lookup"><span data-stu-id="00d6a-118">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="00d6a-119">Все совпадения с реальными наименованиями, людьми и любыми другими предметами являются непреднамеренными и случайными.</span><span class="sxs-lookup"><span data-stu-id="00d6a-119">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="00d6a-120">Microsoft и товарные знаки, перечисленные на странице "Товарные знаки" на сайте http://www.microsoft.com, являются товарными знаками группы компаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="00d6a-120">Microsoft and the trademarks listed at http://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="00d6a-121">Mac и macOS являются товарными знаками Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="00d6a-121">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="00d6a-122">Логотип Docker с изображением кита является зарегистрированным товарным знаком Docker, Inc. Используется с разрешения.</span><span class="sxs-lookup"><span data-stu-id="00d6a-122">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="00d6a-123">Все другие наименования и логотипы являются собственностью своих законных владельцев.</span><span class="sxs-lookup"><span data-stu-id="00d6a-123">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="00d6a-124">Соавторы:</span><span class="sxs-lookup"><span data-stu-id="00d6a-124">Co-Authors:</span></span>

> <span data-ttu-id="00d6a-125">**Сезар де ла Торре** (Cesar de la Torre), старший руководитель проектов, группа разработки .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-125">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="00d6a-126">**Билл Вагнер** (Bill Wagner), старший разработчик содержимого, C+E, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-126">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="00d6a-127">**Майк Роусос** (Mike Rousos), главный специалист по разработке программного обеспечения, команда DevDiv CAT, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-127">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="00d6a-128">Редакторы:</span><span class="sxs-lookup"><span data-stu-id="00d6a-128">Editors:</span></span>

> <span data-ttu-id="00d6a-129">**Майк Поуп** (Mike Pope)</span><span class="sxs-lookup"><span data-stu-id="00d6a-129">**Mike Pope**</span></span>
>
> <span data-ttu-id="00d6a-130">**Стив Хоуг** (Steve Hoag)</span><span class="sxs-lookup"><span data-stu-id="00d6a-130">**Steve Hoag**</span></span>

<span data-ttu-id="00d6a-131">Участники и рецензенты:</span><span class="sxs-lookup"><span data-stu-id="00d6a-131">Participants and reviewers:</span></span>

> <span data-ttu-id="00d6a-132">**Джеффри Рихтер** (Jeffrey Richter), партнер по разработке программного обеспечения, команда Azure, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-132">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="00d6a-133">**Джимми Богард** (Jimmy Bogard), главный архитектор Headspring</span><span class="sxs-lookup"><span data-stu-id="00d6a-133">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="00d6a-134">**Уди Дахан** (Udi Dahan), основатель и генеральный директор компании Particular Software</span><span class="sxs-lookup"><span data-stu-id="00d6a-134">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="00d6a-135">**Джимми Нилссон** (Jimmy Nilsson), сооснователь и генеральный директор компании Factor10</span><span class="sxs-lookup"><span data-stu-id="00d6a-135">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="00d6a-136">**Гленн Кондрон** (Glenn Condron), старший руководитель программ, команда ASP.NET</span><span class="sxs-lookup"><span data-stu-id="00d6a-136">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="00d6a-137">**Марк Фасселл** (Mark Fussell), ведущий руководитель проектов, команда Azure Service Fabric, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-137">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="00d6a-138">**Диего Вега** (Diego Vega), руководитель проектов, команда Entity Framework, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-138">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="00d6a-139">**Барри Дорранс** (Barry Dorrans), старший руководитель программы безопасности</span><span class="sxs-lookup"><span data-stu-id="00d6a-139">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="00d6a-140">**Роуэн Миллер** (Rowan Miller), старший руководитель программы, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-140">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="00d6a-141">**Анкит Астана** (Ankit Asthana), ведущий руководитель проектов, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-141">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="00d6a-142">**Скотт Хантер** (Scott Hunter), помощник главного руководителя проектов, команда .NET, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-142">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="00d6a-143">**Дилан Райзенбергер** (Dylan Reisenberger), архитектор и руководитель разработки, компания Polly</span><span class="sxs-lookup"><span data-stu-id="00d6a-143">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="00d6a-144">**Стив Смит** (Steve Smith), инструктор по разработке программного обеспечения, компания ASPSmith Ltd.</span><span class="sxs-lookup"><span data-stu-id="00d6a-144">**Steve Smith**, Software Craftsman & Trainer at ASPSmith Ltd.</span></span>
>
> <span data-ttu-id="00d6a-145">**Ян Купер** (Ian Cooper), архитектор кода, компания Brighter</span><span class="sxs-lookup"><span data-stu-id="00d6a-145">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="00d6a-146">**Унаи Зоррилла** (Unai Zorrilla), архитектор и руководитель разработки, компания Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="00d6a-146">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="00d6a-147">**Эдуард Томас** (Eduard Tomas), руководитель разработки, компания Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="00d6a-147">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="00d6a-148">**Рамон Томас** (Ramon Tomas), разработчик, компания Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="00d6a-148">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="00d6a-149">**Дэвид Санс** (David Sanz), разработчик, компания Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="00d6a-149">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="00d6a-150">**Хавьер Валеро (Javier Valero)**, исполнительный директор Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="00d6a-150">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="00d6a-151">**Пьер Милле** (Pierre Millet), старший консультант, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-151">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="00d6a-152">**Михаэль Фриис** (Michael Friis), менеджер по продукции, компания Docker Inc</span><span class="sxs-lookup"><span data-stu-id="00d6a-152">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="00d6a-153">**Чарльз Лоуэлл** (Charles Lowell), специалист по разработке программного обеспечения, команда VS CAT, корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="00d6a-153">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="00d6a-154">Вступление</span><span class="sxs-lookup"><span data-stu-id="00d6a-154">Introduction</span></span>

<span data-ttu-id="00d6a-155">Предприятия все шире применяют контейнеры с целью сэкономить средства, решить проблемы, возникающие при разработке решений, и оптимизировать процессы разработки и рабочие операции.</span><span class="sxs-lookup"><span data-stu-id="00d6a-155">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="00d6a-156">Корпорация Майкрософт развивает технологии в области контейнеров для Windows и Linux, создавая такие продукты, как Служба контейнеров Azure и Azure Service Fabric, и сотрудничая с ведущими в отрасли компаниями, такими как Docker, Mesosphere и Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="00d6a-156">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Container Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="00d6a-157">С помощью этих решений для работы с контейнерами организации могут создавать и развертывать приложения с той же скоростью и масштабируемостью, что и в облачной среде, на основе любых платформ и средств.</span><span class="sxs-lookup"><span data-stu-id="00d6a-157">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="00d6a-158">Docker становится стандартом де-факто в области контейнеризации приложений. Это решение поддерживается большинством поставщиков в экосистеме Windows и Linux.</span><span class="sxs-lookup"><span data-stu-id="00d6a-158">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="00d6a-159">(Корпорация Майкрософт — один из основных поставщиков облачных решений, поддерживающих Docker.) В будущем Docker, вероятно, можно будет встретить в любом центре обработки данных как в облаке, так и в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="00d6a-159">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="00d6a-160">Помимо этого, развивается архитектура [микрослужб](https://martinfowler.com/articles/microservices.html), которая представляет собой важный подход к реализации распределенных критически важных приложений.</span><span class="sxs-lookup"><span data-stu-id="00d6a-160">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="00d6a-161">Архитектура на основе микрослужб предполагает создание приложения на базе коллекции служб, которые могут разрабатываться, тестироваться, развертываться и обновляться независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="00d6a-161">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="00d6a-162">Об этом руководстве</span><span class="sxs-lookup"><span data-stu-id="00d6a-162">About this guide</span></span>

<span data-ttu-id="00d6a-163">В этом руководстве приводятся общие сведения о разработке приложений на основе микрослужб и управлении ими с помощью контейнеров.</span><span class="sxs-lookup"><span data-stu-id="00d6a-163">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="00d6a-164">В нем рассматриваются подходы к проектированию и реализации архитектуры с помощью .NET Core и контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="00d6a-164">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="00d6a-165">Чтобы вам было проще приступить к работе с контейнерами и микрослужбами, в руководстве подробно изучается пример контейнерного приложения на основе микрослужб.</span><span class="sxs-lookup"><span data-stu-id="00d6a-165">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="00d6a-166">Пример приложения доступен в репозитории GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="00d6a-166">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="00d6a-167">В этом руководстве приводятся базовые рекомендации по разработке и проектированию архитектуры в первую очередь на уровне среды разработки. Основное внимание уделяется двум технологиям: Docker и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="00d6a-167">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="00d6a-168">Мы ставили себе целью, чтобы при чтении этого руководства вы могли сосредоточиться на проектировании приложения, не задумываясь об инфраструктуре рабочей среды (облачной или локальной).</span><span class="sxs-lookup"><span data-stu-id="00d6a-168">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="00d6a-169">Принимать решения, связанные с инфраструктурой, вы будете позднее при создании приложений, готовых к использованию в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="00d6a-169">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="00d6a-170">Таким образом, это руководство ориентировано на среду разработки без учета особенностей инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="00d6a-170">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="00d6a-171">После изучения этого руководства вашим следующим шагом будет изучение готовых к использованию микрослужб в Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="00d6a-171">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="00d6a-172">Темы, которые выходят за рамки этого руководства</span><span class="sxs-lookup"><span data-stu-id="00d6a-172">What this guide does not cover</span></span>

<span data-ttu-id="00d6a-173">В этом руководстве не рассматриваются такие вопросы, как жизненный цикл приложения, DevOps, конвейеры непрерывной интеграции и непрерывного развертывания, а также совместная работа.</span><span class="sxs-lookup"><span data-stu-id="00d6a-173">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="00d6a-174">Эти темы обсуждаются в дополнительном руководстве [Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт](https://aka.ms/dockerlifecycleebook).</span><span class="sxs-lookup"><span data-stu-id="00d6a-174">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="00d6a-175">В настоящем руководстве также не приводятся сведения о реализации инфраструктуры Azure, например информация о конкретных оркестраторах.</span><span class="sxs-lookup"><span data-stu-id="00d6a-175">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="00d6a-176">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="00d6a-176">Additional resources</span></span>

-   <span data-ttu-id="00d6a-177">**Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт** (электронная книга, доступная для скачивания) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span><span class="sxs-lookup"><span data-stu-id="00d6a-177">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="00d6a-178">Кому необходимо это руководство</span><span class="sxs-lookup"><span data-stu-id="00d6a-178">Who should use this guide</span></span>

<span data-ttu-id="00d6a-179">Мы создали это руководство для разработчиков и архитекторов решений, которые не имеют опыта разработки приложений на основе Docker и работы с архитектурой микрослужб.</span><span class="sxs-lookup"><span data-stu-id="00d6a-179">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="00d6a-180">Воспользуйтесь этим руководством, чтобы узнать, как спроектировать архитектуру и реализовать приложение для проверки концепции с помощью технологий разработки Майкрософт (особое внимание уделяется .NET Core) и контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="00d6a-180">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="00d6a-181">Руководство также может оказаться полезным для лиц, принимающих технические решения, например архитекторов корпоративных систем, которым необходимо получить общие сведения об архитектуре и технологиях, прежде чем выбирать подход для создания современных распределенных приложений.</span><span class="sxs-lookup"><span data-stu-id="00d6a-181">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="00d6a-182">Как пользоваться руководством</span><span class="sxs-lookup"><span data-stu-id="00d6a-182">How to use this guide</span></span>

<span data-ttu-id="00d6a-183">В первой части этого руководства приводятся общие сведения о контейнерах Docker, описываются критерии выбора .NET Core или .NET Framework в качестве платформы разработки и дается обзор микрослужб.</span><span class="sxs-lookup"><span data-stu-id="00d6a-183">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="00d6a-184">Это содержимое предназначено для архитекторов и лиц, принимающих технические решения, которым требуется получить общее представление, не вдаваясь в подробности реализации на уровне кода.</span><span class="sxs-lookup"><span data-stu-id="00d6a-184">This content is for architects and technical decision makers who want an overview but who do not need to focus on code implementation details.</span></span>

<span data-ttu-id="00d6a-185">Вторая часть руководства начинается с раздела [Процесс разработки для приложений на основе Docker](#ch_dev_process_for_docker_based_apps).</span><span class="sxs-lookup"><span data-stu-id="00d6a-185">The second part of the guide starts with the [Development process for Docker based applications](#ch_dev_process_for_docker_based_apps) section.</span></span> <span data-ttu-id="00d6a-186">Он посвящен разработке и шаблонам микрослужб для реализации приложений с помощью .NET Core и Docker.</span><span class="sxs-lookup"><span data-stu-id="00d6a-186">It focuses on development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="00d6a-187">Этот раздел будет особенно интересен разработчикам и архитекторам, которым нужны подробные сведения о реализации на уровне кода и шаблона.</span><span class="sxs-lookup"><span data-stu-id="00d6a-187">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="00d6a-188">Пример приложения на основе микрослужб и контейнеров: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="00d6a-188">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="00d6a-189">eShopOnContainers — это пример приложения для .NET Core и микрослужб, который предназначен для развертывания с помощью контейнеров Docker.</span><span class="sxs-lookup"><span data-stu-id="00d6a-189">The eShopOnContainers application is a reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="00d6a-190">Приложение состоит из нескольких подсистем, включая ряд пользовательских интерфейсов для работы с электронным магазином (веб-приложение и собственное мобильное приложение).</span><span class="sxs-lookup"><span data-stu-id="00d6a-190">The application consists of multiple subsystems, including several e-store UI front ends (a Web app and a native mobile app).</span></span> <span data-ttu-id="00d6a-191">В его состав также входят внутренние микрослужбы и контейнеры для всех необходимых операций на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="00d6a-191">It also includes the back-end microservices and containers for all required server-side operations.</span></span>

<span data-ttu-id="00d6a-192">Исходный код приложения на основе микрослужб и контейнеров является открытым и доступен в репозитории GitHub [eShopOnContainers](http://aka.ms/MicroservicesArchitecture).</span><span class="sxs-lookup"><span data-stu-id="00d6a-192">This microservice and container-based application source code is open source and available at the [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) GitHub repo.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="00d6a-193">Отправьте нам свой отзыв.</span><span class="sxs-lookup"><span data-stu-id="00d6a-193">Send us your feedback!</span></span>

<span data-ttu-id="00d6a-194">Мы создали это руководство, чтобы помочь вам разобраться в архитектуре контейнерных приложений и микрослужб в .NET.</span><span class="sxs-lookup"><span data-stu-id="00d6a-194">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="00d6a-195">Руководство и связанный с ним пример приложения будут развиваться, поэтому мы будем рады вашим отзывам!</span><span class="sxs-lookup"><span data-stu-id="00d6a-195">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="00d6a-196">Если у вас есть замечания касательно того, как можно улучшить этот документ, направляйте их по следующему адресу</span><span class="sxs-lookup"><span data-stu-id="00d6a-196">If you have comments about how this guide can be improved, please send them to:</span></span>

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

>[!div class="step-by-step"]
<span data-ttu-id="00d6a-197">[Далее] (container-docker-introduction/index.md)</span><span class="sxs-lookup"><span data-stu-id="00d6a-197">[Next] (container-docker-introduction/index.md)</span></span>
