---
title: Когда не следует развернуть контейнеры Windows
description: Модернизировать существующие приложения .NET с контейнерами Windows и облако Azure | Когда не следует развернуть контейнеры Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 819f32955ff019414bef8820d17d272eddc11bf8
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Когда не следует развернуть контейнеры Windows

Некоторые технологии Windows не поддерживаются в контейнерах Windows. В таких случаях необходимо для миграции виртуальных машин стандартов, обычно с просто Windows и служб IIS.

Не поддерживается в контейнерах Windows, по состоянию на май 2018 случаи: 

-   Очередь сообщений (MSMQ) в настоящее время доступна только в зависимости от версии Windows Server v1803 контейнерах Windows, но не в предыдущих версиях. 

    -   [Форум по запросу UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [Дискуссионный форум](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Координатор распределенных транзакций (MSDTC) в настоящее время не поддерживается в контейнерах Windows.

    -   [Проблема GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   В настоящее время Microsoft Office не поддерживает контейнеры.

    -   [Форум по запросу UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   Пользовательский Интерфейс приложения (приложения для клиента с с графическим пользовательским интерфейсом), не поддерживаемые сценарии.

-   Роли Windows инфраструктуры (DNS, DHCP-, DC, NTP, печать, файловым сервером, IAM т. д.), не поддерживаемые сценарии.


Дополнительные сценарии не поддерживаются и запросы от сообщества см. на форуме UserVoice для контейнеров Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Виртуальные машины и контейнеры в Azure**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[Назад](deploy-existing-net-apps-as-windows-containers.md)
[Вперед](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
