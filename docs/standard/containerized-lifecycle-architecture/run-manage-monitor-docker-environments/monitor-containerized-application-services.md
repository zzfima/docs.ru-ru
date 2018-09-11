---
title: Мониторинг служб контейнерных приложений
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 4bdc4470624ce6e905ab858a2bd8b607c8d3d646
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275864"
---
# <a name="monitor-containerized-application-services"></a>Мониторинг служб контейнерных приложений

Крайне важно для приложений разбить на несколько контейнеров и микрослужб иметь возможность отслеживать и анализировать поведение приложения.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) — расширяемая Служба аналитики, отслеживающий работающего приложения. Она помогает обнаруживать и диагностировать проблемы с производительностью и понять, что пользователи фактически делают с вашим приложением. Она предназначена для разработчиков, с целью помочь вам в постоянно улучшать производительность и удобство использования служб и приложений. Application Insights работает с веб служб и автономных приложений на самых разных платформ, как .NET, Java, Node.js и многих других платформах, размещенные локально или в облаке.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Анализ приложений Docker в среде контроля Качества, с помощью Application Insights

Поскольку затрагивает как Docker, вы сможете увидеть график события жизненного цикла и счетчики производительности из контейнеров Docker в Application Insights. Необходимо запустить [образ Application Insights Docker](https://hub.docker.com/r/microsoft/applicationinsights/) как контейнер в узле и он будет отображать счетчики производительности для узла, и для других образов Docker. Этот образ Application Insights Docker (рис. 6 - 1) помогает отслеживать контейнерные приложения путем сбора данных телеметрии о производительности и активности узла Docker (то есть виртуальных машин Linux), контейнеры Docker и приложения, выполняющиеся в них.

![пример](./media/image1.png)

Рис. 6-1: Application Insights, мониторинг узлов Docker и контейнеры

При запуске [образ Application Insights Docker](https://hub.docker.com/r/microsoft/applicationinsights/) на узле Docker, можно воспользоваться преимуществами следующих:

-   Данные телеметрии о всех контейнеров, запущенных на узле жизненного цикла — запустить, остановить и т. д.

-   Счетчики производительности для всех контейнеров: ЦП, памяти, использование сети и многое другое.

-   Если вы установили также [пакет SDK Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) в приложениях, выполняющихся в контейнерах, все данные телеметрии этих приложений будут иметь дополнительные свойства, идентифицирующие контейнер и хост-компьютер. Таким образом например, если у вас есть экземпляры приложения, запущенные на нескольких узлах, вы легко сможете отфильтровать данные телеметрии приложения по узлу.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Настройка Application Insights для мониторинга приложений Docker и узлов Docker

Чтобы создать ресурс Application Insights, следуйте инструкциям в статьях, представленных в списке ниже. Портал Azure создаст необходимый скрипт для вас.

-   **Мониторинг приложений Docker в Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **Приложения Insights Docker образ в Docker Hub и Github:**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) и <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **Настройка Application Insights для ASP.NET:**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **Application Insights для веб-страниц:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](https://microsoft.com/oms) — это упрощенное решение управления ИТ, которое предоставляет log analytics, автоматизации, архивации и site recovery. На основе [запросы](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) в Operations Management Suite, вы можете отправить [оповещения](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) и установить исправление через [службы автоматизации Azure](https://docs.microsoft.com/azure/automation/). Оно также легко интегрируется в существующие решения управления для обеспечения единого представления панели прозрачного стекла. Operations Management Suite помогает управлять и защищать в локальной и облачной инфраструктурой.

### <a name="operations-management-suitehttpsmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](https://microsoft.com/oms) решение контейнеров для Docker

Помимо предоставления ценных служб, сам по себе, решение контейнера для операций управления Suite можно управлять и отслеживать узлы Docker и контейнеры, отображая сведения о размещении контейнеров и узлов контейнеров, какие контейнеры запущены или в состоянии сбоя и Docker daemon и контейнер журналов, отправляемых в *stdout* и *stderr*. Оно также показывает метрики производительности, такие как загрузка ЦП, объем памяти, характеристики сети и хранилища для контейнера и узлов, чтобы помочь устранить ошибки и обнаружить конфликтующие соседние контейнеры.

![](./media/image2.png)

Рис. 6-2: сведения о контейнерах Docker, представленной в Operations Management Suite

Application Insights и Operations Management Suite сосредоточиться на мониторинга действий; Тем не менее Application Insights больше фокусируется на наблюдение за приложениями сами благодаря этот пакет SDK в приложение. Тем не менее Operations Management Suite гораздо больше фокусируется на инфраструктуре вокруг узлов, а также он предлагает глубокий анализ журналов в масштабе то же время предоставляя системе очень гибкий управляемых данными поиска и запроса.

Так как Operations Management Suite реализуется как облачная служба, возможно он приступить к работе быстро с минимальными затратами на службы инфраструктуры. Новые возможности предоставляются автоматически, что на текущее обслуживание и обновление затраты.

С помощью Operations Management Suite контейнер решения, можно сделать следующее:

-   Централизовать и сопоставлять миллионам журналов из контейнеров Docker в нужном масштабе

-   Просмотреть сведения о всех узлов контейнера в одном месте

-   Знать, какие контейнеры запущенных, какой образ их работы и где они выполняются:

-   Быстро диагностировать контейнеры «шумный сосед», которые могут вызвать проблемы на узлах контейнера

-   Журнал аудита для действий см. в разделе о контейнерах

-   Устранение неполадок путем просмотра и поиска централизованные журналы без удаленного взаимодействия с узлами Docker

-   Находить контейнеры, которые могут быть «шумных соседей» и занимает слишком много ресурсов на узле

-   Просмотреть централизованного ЦП, памяти, хранения и сведения об использовании и производительности сети для контейнеров

-   Создать тестовые контейнеры Docker с помощью службы автоматизации Azure

Вы увидите сведения о производительности с помощью запросов, такие как тип = Perf, как показано на рис. 6-3.

![DockerPerfMetricsView](./media/image3.png){width = «5.78625 in» height = «3,25 in»}

Рис. 6-3: метрики производительности узлов Docker, представленной в Operations Management Suite

Сохранение запросов также — это стандартная функция в Operations Management Suite, которая помогает сохранять запросы, оказавшиеся полезными и трендов в вашей системе.

**Дополнительные сведения о** для поиска сведений об установке и настройке Docker решение для контейнеров в [Operations Management Suite](https://microsoft.com/oms), перейдите в меню <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.

>[!div class="step-by-step"]
[Назад](manage-production-docker-environments.md)
[Вперед](../key-takeaways/index.md)
