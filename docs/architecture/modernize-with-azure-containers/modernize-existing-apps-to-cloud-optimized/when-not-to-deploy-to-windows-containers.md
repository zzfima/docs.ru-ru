---
title: Технологии, не поддерживающие развертывание в контейнерах Windows
description: Модернизировать существующих приложений .NET с помощью Azure Cloud and Windows Containers | Когда не следует развертывать контейнеры Windows
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577957"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Технологии, не поддерживающие развертывание в контейнерах Windows

Некоторые технологии Windows не поддерживаются контейнерами Windows. В таких случаях вам по-прежнему нужно выполнить миграцию на виртуальные машины Standard, обычно с помощью только Windows и IIS.

Варианты не поддерживаются в контейнерах Windows, начиная с 2018 мая:

- В настоящее время служба очередей сообщений (MSMQ) доступна только в контейнерах Windows, основанных на выпуске Windows Server v1803, но не в других предыдущих выпусках.

  - [Форум по запросам UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Форум обсуждений](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- В настоящее время в контейнерах Windows не поддерживается Microsoft координатор распределенных транзакций (MSDTC).

  - [Проблемы GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Microsoft Office в настоящее время не поддерживает контейнеры.

  - [Форум по запросам UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- Приложения пользовательского интерфейса (клиентские приложения с визуальным пользовательским интерфейсом) не поддерживаются.

- Роли инфраструктуры Windows (DNS, DHCP, DC, NTP, PRINT, файловый сервер, IAM и т. д.) не поддерживаются.

Дополнительные неподдерживаемые сценарии и запросы от сообщества см. на форуме UserVoice для контейнеров Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Виртуальные машины и контейнеры в Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Назад](deploy-existing-net-apps-as-windows-containers.md)
> [Вперед](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
