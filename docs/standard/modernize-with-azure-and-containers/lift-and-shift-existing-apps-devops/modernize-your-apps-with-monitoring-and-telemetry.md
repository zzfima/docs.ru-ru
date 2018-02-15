---
title: "Модернизировать приложений с помощью мониторинга и данные телеметрии"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Модернизировать приложений с помощью мониторинга и данные телеметрии"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1535951eb648deab17cf8c2fe64db6ddf7df4cb5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Модернизировать приложений с помощью мониторинга и данные телеметрии

При запуске приложения в рабочей среде, важно наличие ценной информации о том, как работает приложение. Работает на высоком уровне? Пользователи получении ошибок или нестабильной или ненадежной, — это приложение? Требуется наблюдение за производительностью форматированного мощные оповещения и панели мониторинга, чтобы гарантировать наличие приложения доступны и выполняется должным образом. Необходимо также иметь возможность быстро см, если имеется проблема, определить, сколько клиентов затрагиваются и анализ основной причины, чтобы найти и устранить ее.

## <a name="monitor-your-application-with-application-insights"></a>Наблюдать за приложением с помощью Application Insights

Аналитика приложений — расширяемую службу управления производительностью приложений (APM) для веб-разработчиков, работающих на нескольких платформах. Используйте ее для мониторинга динамической веб-приложения. Application Insights автоматически обнаруживает аномалий производительности. Она также включает средства гибкой аналитической для выявления проблем и поможет вам понять, какие пользователи фактически выполняют вместе с приложением. Application Insights поможет постоянно улучшать производительность и удобство использования. Он работает для приложений на разнообразных платформах, включая .NET, Node.js и J2EE ли размещается локально или в облаке. Application Insights интегрируется с DevOps процессов и имеет точек подключения для различных средств разработки.

Рис. 4-10 является примером как Application Insights мониторинг приложения и как он перехватывает эту информацию на панель мониторинга.

![Панель мониторинга Application Insights](./media/image10.png)

> **Рис. 4-10.** Панель мониторинга Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Отслеживать состояние инфраструктуры Docker с анализа журналов и его решение для наблюдения за контейнера

[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) является частью [Microsoft Azure общее решение по мониторингу](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). Он также представляет собой службу [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Аналитика журналов наблюдает за облачной и локальной среде (OMS для локальной) в целях обеспечения доступности и производительности. Он собирает данные, созданные ресурсы облака и локальных сред и в другие средства мониторинга для обеспечения аналитики в нескольких источников.

Относительно журналы инфраструктуры Azure службы анализа журналов, как службу Azure принимает данные журнала и метрики из других служб Azure (через [монитора Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), виртуальные машины Azure, контейнеры Docker и локальной или других облачных инфраструктур. Аналитика журналов предлагает поиска журналов гибкие и аналитика out поле на основе этих данных. Он предоставляет широкие возможности средства можно использовать для анализа ко всем источникам данных, он позволяет сложных запросов через все журналы, и можно заранее предупредить на основании указанных условий. Можно даже сбора пользовательских данных в центральный репозиторий анализа журналов, где можно запрашивать и визуализировать их. Можно также пользоваться преимуществами анализа журналов встроенные решения для сразу же получать подробные сведения о безопасности и функциональных возможностей инфраструктуры.

Можно получить доступ к службе анализа журналов на портале OMS или портал Azure, которые выполняются в любом браузере, и предоставить вам доступ к параметрам конфигурации и несколько средств для анализа и выполнения соответствующих собранных данных.

[Решения отслеживания контейнера](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) в аналитика журналов позволяет просматривать и управлять ими узлах Docker и контейнера Windows в одном месте. Объясняется, какие контейнеры — под управлением какой образ контейнера они выполняются, и запущенным контейнеров. Можно просмотреть подробные сведения аудита, включая команды, используемые с контейнерами. Контейнеры также можно устранить путем просмотра и поиска централизованные журналы, без необходимости удаленно просматривать узлы Docker или Windows. Можно найти контейнеры, которые могут быть шум и требующим много огромные ресурсы на узле. Кроме того можно просмотреть централизованного ЦП, памяти, хранилища и использования сети и сведения о производительности для контейнеров. На компьютерах под управлением Windows, можно централизовать и сравнить журналы с сервера Windows Hyper-V и контейнеров Docker. Решение поддерживает следующие orchestrators контейнера:

-   Docker группу мелких объектов

-   DC/OS

-   Kubernetes

-   Service Fabric

-   Red Hat OpenShift

Рис. 4-11 взаимосвязи между различными узлы контейнера и агенты и OMS.

![Решения отслеживания контейнера аналитика журналов](./media/image11.png)

> **Рис. 4-11.** Решения отслеживания контейнера аналитика журналов

Можно использовать решение отслеживания контейнера аналитика журналов:

-   Просмотреть сведения о всех узлов контейнера в одном месте.

-   Знать, какие контейнеры запущен, какое изображение они выполняются, и где они запущены.

-   См. журнал аудита для операций в контейнерах.

-   Устранение неполадок путем просмотра и поиска централизованные журналы без удаленного входа на узлах Docker.

-   Найти контейнеров, которые могут быть «шумный соседей» и потребляют огромные ресурсы на узле.

-   Просмотр централизованного ЦП, памяти, хранилища и использования сети и сведения о производительности для контейнеров.

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Обзор наблюдения за Microsoft Azure**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)

-   **Что такое Application Insights?**

[https://docs.microsoft.com/azure/application-insights/app-insights-overview](https://docs.microsoft.com/azure/application-insights/app-insights-overview)

-   **Новые возможности анализа журналов**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-overview](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)

-   **Решение мониторинг контейнера в службе анализа журналов**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-containers](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)

-   **Общие сведения о мониторе Azure**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)

-   **Новые возможности Operations Management Suite (OMS)**

[https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

-   **Наблюдение за контейнеры Windows Server в Service Fabric с OMS**

[https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver](https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver)

>[!div class="step-by-step"]
[Назад](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Вперед](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
