---
title: "Когда не следует развернуть контейнеры Windows"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Когда не следует развернуть контейнеры Windows"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c74b71f9c80ab51cabe0e3c4abf32f292da30763
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Когда не следует развернуть контейнеры Windows

Некоторые технологии Windows не поддерживаются в контейнерах Windows. В таких случаях необходимо для миграции виртуальных машин стандартов, обычно с просто Windows и служб IIS.

Случаи, не поддерживается в контейнерах Windows, начиная с mid 2017 г.:

-   Очередь сообщений (MSMQ) в настоящее время не поддерживается в контейнерах Windows.

    -   [Форум по запросу UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [Дискуссионный форум](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Координатор распределенных транзакций (MSDTC) в настоящее время не поддерживается в контейнерах Windows

    -   [Проблема GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office в настоящее время не поддерживает контейнеры

    -   [Форум по запросу UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

Дополнительные сценарии не поддерживаются и запросы от сообщества см. на форуме UserVoice для контейнеров Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Виртуальные машины и контейнеры в Azure**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[Назад](deploy-existing-net-apps-as-windows-containers.md)
[Вперед](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
