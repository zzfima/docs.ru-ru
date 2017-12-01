---
title: "Монитор контейнерных приложений служб"
description: "Жизненный цикл приложений контейнерного Docker с помощью платформы Майкрософт и средств"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3e4a78eb47d0e6712919c89b6f52ec8e4248fb23
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2017
---
# <a name="monitor-containerized-application-services"></a>Монитор контейнерных приложений служб

Очень важно для приложений, разбить на несколько контейнеров и микрослужбами, чтобы иметь возможность отслеживать и анализировать поведение приложения.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) — это расширяемый analytics служба, которая отслеживает работающего приложения. Он помогает выявить и диагностировать проблемы с производительностью и понять, какие пользователи фактически иметь вместе с приложением. Она предназначена для разработчиков, с целью помочь вам в постоянно повысить производительность и удобство использования служб и приложений. Application Insights работает с веб служб и автономные приложения на самых разных платформ, как .NET, Java, Node.js и многих других платформах размещается локально или в облаке.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Анализ приложения Docker в средах QA, с помощью Application Insights

Поскольку относится к Docker, можно диаграммы жизненного цикла события и счетчики производительности из контейнеров Docker в Application Insights. Необходимо запустить [образа Docker аналитики приложений](https://hub.docker.com/r/microsoft/applicationinsights/) как контейнер в узле, который отображает счетчики производительности для узла, и для других образов Docker. Этот образ Docker аналитики приложения (на рисунке 6 - 1) помогает отслеживать приложений в контейнерах, предоставив возможность сбора данных телеметрии о производительности и активности (то есть виртуальные машины Linux) узла Docker, контейнеры Docker и приложениями, работающими в них.

![пример](./media/image1.png)

Мониторинг узлов Docker и контейнеры Application Insights рис. 6-1.

При запуске [образа Docker аналитики приложений](https://hub.docker.com/r/microsoft/applicationinsights/) на узле Docker, можно воспользоваться преимуществами следующих:

-   Жизненный цикл данных телеметрии о всех контейнеров, работающих на узле, запуск, остановка и т. д.

-   Счетчики производительности для всех контейнеров: ЦП, памяти, использование сети и многое другое.

-   Если вы установили также [пакет SDK Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) в приложений, выполняющихся в контейнерах, все данные телеметрии эти приложения будут иметь дополнительные свойства, определение контейнера и узла компьютера. Таким образом например, при наличии экземпляров приложения, работающего в более чем одному узлу, вы легко сможете фильтровать данные телеметрии вашего приложения узлом.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Чтобы настроить Application Insights для наблюдения за приложениями Docker и узлах Docker

Чтобы создать ресурс Application Insights, следуйте инструкциям в статьях, представленных в списке ниже. Портал Azure создаст необходимый скрипт для вас.

-   **Наблюдение за приложениями Docker в Application Insights:**[https://docs.microsoft.com/azure/application-insights/app-insights-docker  ](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **Образ Docker аналитики приложений в Docker Hub и Github:**  
[https://Hub.docker.com/r/Microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) и <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **Настройте Application Insights для ASP.NET:**  
[https://docs.Microsoft.com/Azure/Application-Insights/App-Insights-ASP-NET](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **Application Insights для веб-страниц:**  
<https://docs.Microsoft.com/Azure/Application-Insights/App-Insights-JavaScript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](http://microsoft.com/oms) — упрощенное решение для управления ИТ, предоставляющий службы анализа журналов, автоматизации, архивации и site recovery. На основе [запросы](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) в Operations Management Suite может вызвать [оповещения](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) и установите исправление через [автоматизации Azure](https://docs.microsoft.com/azure/automation/). Он также легко интегрируется с существующие решения управления для предоставления единого представления панели из стекла. Operations Management Suite позволяет управлять и защиты в локальной и облачной инфраструктуры.

### <a name="operations-management-suitehttpmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](http://microsoft.com/oms) решение контейнера для Docker

Помимо ценных сам по себе, решение контейнера набор операций управления можно управлять и отслеживать узлах Docker и контейнеры, отображая сведения о размещении контейнеры и узлы контейнера, какие контейнеры запущены или в состоянии сбоя, Docker daemon контейнера и журналы и отправляемые *stdout* и *stderr*. Он также показывает метрики производительности, такие как ЦП, памяти, сети и хранилища для контейнера и узлы для помогают устранить ошибки и найти шумный сосед контейнеров.

![](./media/image2.png)

Рис. 6-2: сведения о контейнерах Docker, представленной в Operations Management Suite

Application Insights и Operations Management Suite сосредоточиться на наблюдение за операциями; Тем не менее Application Insights более сосредоточен на наблюдении за самих приложений благодаря его SDK, запущенного в рамках приложения. Однако Operations Management Suite гораздо более уделяется инфраструктуры вокруг узлов, а также предлагает глубокий анализ журналов в масштабе то же время предоставляя системы очень гибкий управляемых данными поиска или запрос.

Operations Management Suite, реализованные в виде облачной службы, что он работает быстро с минимальными затратами на службы инфраструктуры. Новые возможности предоставляются автоматически, позволит избежать текущее обслуживание и обновление затрат.

С помощью Operations Management Suite контейнер решения, можно сделать следующее:

-   Централизовать и сопоставлять миллионы журналы из контейнеров Docker в масштабе

-   Просмотреть сведения о всех узлов контейнера в одном месте

-   Знать, какие контейнеры запущен, какое изображение они выполняются, и где они запущены

-   Быстро найти причину контейнеры «шумный сосед», может отрицательно сказаться на узлы контейнера

-   См. журнал аудита для операций в контейнерах

-   Устранение неполадок путем просмотра и поиска централизованные журналы без удаленного взаимодействия с узлами Docker

-   Найти контейнеры, которые могут быть «шумный соседей» и много огромные ресурсы на узле

-   Просмотр централизованного ЦП, памяти, хранилища и сведения об использовании и производительности сети для контейнеров

-   Создать тестовые контейнеры Docker в службе автоматизации Azure

Сведения о производительности можно увидеть с помощью запросов, такие как тип = производительности, как показано на рисунке 6-3.

![DockerPerfMetricsView](./media/image3.png){width = «5.78625 in» высота = «3,25 in»}

Рис. 6-3: метрики производительности узлах Docker, представленной в Operations Management Suite

Сохранение запросов также является стандартным компонентом в Operations Management Suite и помогут вам поддерживать запросы нахожу полезным и трендов в системе.

**Дополнительные сведения о** для поиска сведений об установке и настройке Docker решение контейнера в [Operations Management Suite](http://microsoft.com/oms), перейдите в меню <https://docs.microsoft.com/azure/ Журнал analytics/журнала аналитика контейнеры>.

>[!div class="step-by-step"]
[Предыдущие] (Управление производственного docker-environments.md) [Далее] (.. /Key-takeaways/index.MD)
