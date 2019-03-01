---
title: Мониторинг служб контейнерных приложений
description: Узнайте, некоторые ключевые аспекты мониторинга контейнера архитектуры
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 925db543617deb28590cf6631ebbda3ee96836c4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975749"
---
# <a name="monitor-containerized-application-services"></a>Мониторинг служб контейнерных приложений

Крайне важно для приложений разбить на несколько контейнеров и микрослужб иметь возможность отслеживать и анализировать поведение всего приложения.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) — расширяемая Служба аналитики, отслеживающий работающего приложения. Она помогает обнаруживать и диагностировать проблемы с производительностью и понять, что пользователи фактически делают с вашим приложением. Она предназначена для разработчиков, с целью помочь вам в постоянно улучшать производительность и удобство использования служб и приложений. Application Insights работает с веб служб и автономных приложений на самых разных платформ, как .NET, Java, Node.js и многих других платформах, размещенные локально или в облаке.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Анализ приложений Docker в среде контроля Качества, с помощью Application Insights

Поскольку затрагивает как Docker, вы сможете увидеть график события жизненного цикла и счетчики производительности из контейнеров Docker в Application Insights. Необходимо запустить [образ Application Insights Docker](https://hub.docker.com/r/microsoft/applicationinsights/) как контейнер в узле и он будет отображать счетчики производительности для узла, и для других образов Docker. Этот образ Application Insights Docker (рис. 6 - 1) помогает отслеживать контейнерные приложения путем сбора данных телеметрии о производительности и активности узла Docker (то есть виртуальных машин Linux), контейнеры Docker и приложения, выполняющиеся в них.

![пример](./media/image1.png)

**Рис. 6-1**. Application Insights, мониторинг узлов Docker и контейнеры

При запуске [образ Application Insights Docker](https://hub.docker.com/r/microsoft/applicationinsights/) на узле Docker, можно воспользоваться преимуществами следующих:

- Данные телеметрии о всех контейнеров, запущенных на узле жизненного цикла — запустить, остановить и т. д.

- Счетчики производительности для всех контейнеров: ЦП, памяти, использование сети и многое другое.

- Если вы установили также [пакет SDK Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) в приложениях, выполняющихся в контейнерах, все данные телеметрии этих приложений будут иметь дополнительные свойства, идентифицирующие контейнер и хост-компьютер. Таким образом например, если у вас есть экземпляры приложения, запущенные на нескольких узлах, вы легко сможете отфильтровать данные телеметрии приложения по узлу.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Настройка Application Insights для мониторинга приложений Docker и узлов Docker

Чтобы создать ресурс Application Insights, следуйте инструкциям в статьях, представленных в списке ниже. Портал Azure создаст необходимый скрипт для вас.

- **Мониторинг приложений Docker в Application Insights:** \
  <https://docs.microsoft.com/azure/application-insights/app-insights-docker>

- **Приложения Insights Docker образ в Docker Hub и GitHub:** \
  <https://hub.docker.com/r/microsoft/applicationinsights/> и \
  <https://github.com/Microsoft/ApplicationInsights-Docker>

- **Настройка Application Insights для веб-приложений ASP.NET и ASP.NET Core:** \
  <https://docs.microsoft.com/azure/application-insights/app-insights-asp-net>

- **Application Insights для веб-страниц:**  
  <https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="security-backup-and-monitoring-services"></a>Безопасности, архивации и мониторинга служб

Существует множество поддержки кода с большим количеством сведения, которые необходимо обрабатывать для обеспечения приложений и инфраструктуры в верхнем деление условие для поддержки бизнес-потребностей, и ситуация становится более сложных в мире микрослужб, поэтому нужен способ При необходимости предпринять действия, имеют высокого уровня и подробные представления.

Azure предлагает инструменты для управления и предоставления унифицированного представления из четырех важных аспектов облачным и локальным ресурсам:

- **Безопасность**. С помощью [центра безопасности](https://azure.microsoft.com/services/security-center/).
  - Получите полную видимость и контроль безопасности виртуальных машин, приложений и рабочих нагрузок.
  - Централизованное управление политиками безопасности и интегрировать существующие процессы и средства.
  - Обнаруживать реальные угрозы расширенной аналитики.

- **Резервное копирование**. С помощью [служба архивации Azure](https://azure.microsoft.com/services/backup/).
  - Избежать дорогостоящего прерывания работы, удовлетворить требования соответствия и защиты данных от программ-шантажистов, а также человеческих ошибок.
  - Храните данные резервного копирования, шифрования при передаче и хранении.
  - Обеспечить доступ на основе многофакторной проверки подлинности для предотвращения несанкционированного использования.

- **Мониторинг**. С помощью [мониторинг Azure](https://azure.microsoft.com/solutions/monitoring/), [Log Analytics](https://azure.microsoft.com/services/log-analytics/), и [Application Insights](https://azure.microsoft.com/services/application-insights/).
  - Получите подробные сведения о работоспособности и производительности рабочих нагрузок в Azure, приложения и инфраструктуру.
  - Собирать данные из любого источника и получать аналитическую информацию в виртуальные машины, контейнеры и приложения.
  - Поиск необходимой информации с помощью интерактивных запросов и компонент full-text search. 
  - Выполните анализ основной причины расширенные средства аналитики, включая алгоритмы машинного обучения.

- **К локальным ресурсам**. С помощью [действительно согласованное гибридное облако](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).

>[!div class="step-by-step"]
>[Назад](manage-production-docker-environments.md)
>[Вперед](../key-takeaways/index.md)
