---
title: Мониторинг служб контейнерных приложений
description: Узнайте, некоторые ключевые аспекты мониторинга контейнера архитектуры
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 4553a35c8db6cfc46187525ef2ffc65cb3ba07c9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672052"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="11514-103">Мониторинг служб контейнерных приложений</span><span class="sxs-lookup"><span data-stu-id="11514-103">Monitor containerized application services</span></span>

<span data-ttu-id="11514-104">Крайне важно для приложений разбить на несколько контейнеров и микрослужб иметь возможность отслеживать и анализировать поведение всего приложения.</span><span class="sxs-lookup"><span data-stu-id="11514-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="11514-105">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="11514-105">Azure Monitor</span></span>

<span data-ttu-id="11514-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) — расширяемая Служба аналитики, отслеживающий работающего приложения.</span><span class="sxs-lookup"><span data-stu-id="11514-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="11514-107">Она помогает обнаруживать и диагностировать проблемы с производительностью и понять, что пользователи фактически делают с вашим приложением.</span><span class="sxs-lookup"><span data-stu-id="11514-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="11514-108">Она предназначена для разработчиков, с целью помочь вам в постоянно улучшать производительность и удобство использования служб и приложений.</span><span class="sxs-lookup"><span data-stu-id="11514-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="11514-109">Azure Monitor работает с веб служб и автономных приложений на самых разных платформ, как .NET, Java, Node.js и многих других платформах, размещенные локально или в облаке.</span><span class="sxs-lookup"><span data-stu-id="11514-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="11514-110">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="11514-110">Additional resources</span></span>

- <span data-ttu-id="11514-111">**Обзор Azure Monitor** \\</span><span class="sxs-lookup"><span data-stu-id="11514-111">**Overview of Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="11514-112">**Что такое Azure Application Insights?**</span><span class="sxs-lookup"><span data-stu-id="11514-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="11514-113">**Что такое метрики Azure Monitor?**</span><span class="sxs-lookup"><span data-stu-id="11514-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="11514-114">**Решение для мониторинга контейнеров в Azure Monitor** \\</span><span class="sxs-lookup"><span data-stu-id="11514-114">**Container Monitoring solution in Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="11514-115">Службы безопасности и резервного копирования</span><span class="sxs-lookup"><span data-stu-id="11514-115">Security and backup services</span></span>

<span data-ttu-id="11514-116">Существует множество поддержки кода с большим количеством сведения, которые необходимо обрабатывать для обеспечения приложений и инфраструктуры в верхнем деление условие для поддержки бизнес-потребностей, и ситуация становится более сложных в мире микрослужб, поэтому нужен способ При необходимости предпринять действия, имеют высокого уровня и подробные представления.</span><span class="sxs-lookup"><span data-stu-id="11514-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="11514-117">Azure предлагает инструменты для управления и предоставления унифицированного представления из четырех важных аспектов облачным и локальным ресурсам:</span><span class="sxs-lookup"><span data-stu-id="11514-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="11514-118">**Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="11514-118">**Security**.</span></span> <span data-ttu-id="11514-119">С помощью [центра безопасности](https://azure.microsoft.com/services/security-center/).</span><span class="sxs-lookup"><span data-stu-id="11514-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="11514-120">Получите полную видимость и контроль безопасности виртуальных машин, приложений и рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="11514-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="11514-121">Централизованное управление политиками безопасности и интегрировать существующие процессы и средства.</span><span class="sxs-lookup"><span data-stu-id="11514-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="11514-122">Обнаруживать реальные угрозы расширенной аналитики.</span><span class="sxs-lookup"><span data-stu-id="11514-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="11514-123">**Резервное копирование**.</span><span class="sxs-lookup"><span data-stu-id="11514-123">**Backup**.</span></span> <span data-ttu-id="11514-124">С помощью [служба архивации Azure](https://azure.microsoft.com/services/backup/).</span><span class="sxs-lookup"><span data-stu-id="11514-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="11514-125">Избежать дорогостоящего прерывания работы, удовлетворить требования соответствия и защиты данных от программ-шантажистов, а также человеческих ошибок.</span><span class="sxs-lookup"><span data-stu-id="11514-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="11514-126">Храните данные резервного копирования, шифрования при передаче и хранении.</span><span class="sxs-lookup"><span data-stu-id="11514-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="11514-127">Обеспечить доступ на основе многофакторной проверки подлинности для предотвращения несанкционированного использования.</span><span class="sxs-lookup"><span data-stu-id="11514-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="11514-128">**К локальным ресурсам**.</span><span class="sxs-lookup"><span data-stu-id="11514-128">**On-premises resources**.</span></span> <span data-ttu-id="11514-129">С помощью [действительно согласованное гибридное облако](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span><span class="sxs-lookup"><span data-stu-id="11514-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="11514-130">[Назад](manage-production-docker-environments.md)
>[Вперед](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="11514-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
