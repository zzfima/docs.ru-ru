---
title: "Технологии Майкрософт devops готовую для облачных приложений"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Технологии Майкрософт DevOps готовую для облачных приложений"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3212bf1e938b789d68ca76dd06ce53a2788244b6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="microsoft-technologies-in-cloud-devops-ready-applications"></a>Технологии Майкрософт devops готовую для облачных приложений

Ниже перечислены средства, технологий и решений, которые распознаются как требования к DevOps готовую для облачных приложений. В зависимости от вашей приоритеты можно выборочно или делать это постепенно принимают DevOps готовую для облачных приложений.

-   **Облачной инфраструктуры**: инфраструктуры, которая позволяет вычислительных платформ, операционной системы, сети и хранилища. На этом уровне располагается Microsoft Azure.

-   **Среда выполнения**: этот уровень предоставляет среду для запуска приложения. Если вы используете контейнеры, этот уровень обычно основан на [подсистемы Docker](https://docs.docker.com/engine/), работающей на узлах Linux или на узлах Windows. ([Контейнеры Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) поддерживаются начиная с Windows Server 2016. Контейнеры Windows отлично подходит для существующих приложений .NET Framework, работающих под управлением Windows).

-   **Управляемые облака**: при выборе параметра управляемой облачной можно избежать лишних затрат и сложности, управлении и поддержке базовой инфраструктуры виртуальных машин, исправлений ОС и конфигурацию сети. Если вы решите перенести с помощью IaaS, вы отвечаете все эти задачи и сопутствующие затраты. В параметре управляемой облачной управлять только приложения и службы, разрабатываемые. Поставщик облачных служб обычно управляет все остальное. Примеры управляемых облачных служб в Azure [базы данных SQL Azure](https://azure.microsoft.com/services/sql-database), [кэш Azure Redis](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [хранилища Azure](https://azure.microsoft.com/services/storage/), [Базы данных azure для MySQL](https://azure.microsoft.com/services/mysql/), [базы данных Azure для PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)и управляемых служб вычислений, таких как [масштабирования виртуальных Машин Задает](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [службе приложений Azure](https://azure.microsoft.com/services/app-service/), и [контейнера службы Azure](https://azure.microsoft.com/services/container-service/).

-   **Разработка приложений**: можно выбрать из многих языков при построении приложений, работающих в контейнерах. В этом руководстве мы сосредоточим внимание на [.NET](https://www.microsoft.com/net), но можно разрабатывать приложения на основе контейнера с помощью других языках, таких как Node.js, Python, Spring/Java или GoLang.

-   **Мониторинг телеметрии, ведение журнала и аудит**: для любого приложения, готовую для облачных DevOps важна возможность монитора и аудит приложения и контейнеров, которые выполняются в облаке. [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) и [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) основные средства Microsoft, которые обеспечивают мониторинг и аудит для DevOps готовую для облачных приложений.

-   **Подготовка**: средства автоматизации поможет подготовить инфраструктуру и развернуть приложение в различных средах (рабочую среду тестирования, промежуточного хранения). Такие средства, как Chef и Puppet можно использовать для управления конфигурации и среды приложения. Этот уровень также можно реализовать с помощью более простой и более прямой подход. Например, можно развернуть напрямую с помощью Azure командной строки (CLI Azure) для работы с проектами и затем использовать непрерывного развертывания и управления конвейеры в выпуске [Visual Studio Team Services](https://www.visualstudio.com/team-services/).

-   **Жизненный цикл приложений**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) и других средств, таких как Jenkins, являются серверы автоматизации сборки, которые помогают реализовать CI/CD конвейеров, включая управления выпусками.

В последующих разделах данной главы и связанные пошаговые руководства, связана именно с сведения о уровня среды выполнения (контейнеров Windows). Руководство описывает способы, можно развернуть виртуальные машины контейнеры Windows в Windows Server 2016 (и более поздних версиях). Она также охватывает более сложных orchestrator слои, как Azure Service Fabric, Kubernetes и контейнера службы Azure. Настройка уровней orchestrator ― это основополагающее требование для модернизация существующие .NET Framework (Windows) приложения как DevOps готовую для облачных приложений.

## <a name="monolithic-applications-can-be-cloud-devops-ready"></a>Монолитные приложения *можно* быть готовую для облачных DevOps

Очень важно выделить которых монолитные приложения (приложения, которые не основаны на микрослужбами) *можно* быть DevOps готовую для облачных приложений. Можно создать и работать монолитные приложения, использующие преимущества облачных вычислительных модели, используя сочетание контейнеры, непрерывной поставки и DevOps. Если существующее приложение монолитные подходит для ваших бизнес-целей, можно модернизировать его и сделать его готовую для облачных DevOps.

Аналогично Если монолитные приложения могут быть DevOps готовую для облачных приложений, других, более сложные архитектуры, как N-уровневого приложения также могут быть модернизированный и как DevOps готовую для облачных приложений.

>[!div class="step-by-step"]
[Назад](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)
[Вперед](what-about-cloud-optimized-applications.md)
