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
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="d439f-103">Технологии, не поддерживающие развертывание в контейнерах Windows</span><span class="sxs-lookup"><span data-stu-id="d439f-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="d439f-104">Некоторые технологии Windows не поддерживаются контейнерами Windows.</span><span class="sxs-lookup"><span data-stu-id="d439f-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="d439f-105">В таких случаях вам по-прежнему нужно выполнить миграцию на виртуальные машины Standard, обычно с помощью только Windows и IIS.</span><span class="sxs-lookup"><span data-stu-id="d439f-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="d439f-106">Варианты не поддерживаются в контейнерах Windows, начиная с 2018 мая:</span><span class="sxs-lookup"><span data-stu-id="d439f-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="d439f-107">В настоящее время служба очередей сообщений (MSMQ) доступна только в контейнерах Windows, основанных на выпуске Windows Server v1803, но не в других предыдущих выпусках.</span><span class="sxs-lookup"><span data-stu-id="d439f-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="d439f-108">Форум по запросам UserVoice</span><span class="sxs-lookup"><span data-stu-id="d439f-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="d439f-109">Форум обсуждений</span><span class="sxs-lookup"><span data-stu-id="d439f-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="d439f-110">В настоящее время в контейнерах Windows не поддерживается Microsoft координатор распределенных транзакций (MSDTC).</span><span class="sxs-lookup"><span data-stu-id="d439f-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="d439f-111">Проблемы GitHub</span><span class="sxs-lookup"><span data-stu-id="d439f-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="d439f-112">Microsoft Office в настоящее время не поддерживает контейнеры.</span><span class="sxs-lookup"><span data-stu-id="d439f-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="d439f-113">Форум по запросам UserVoice</span><span class="sxs-lookup"><span data-stu-id="d439f-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="d439f-114">Приложения пользовательского интерфейса (клиентские приложения с визуальным пользовательским интерфейсом) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d439f-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="d439f-115">Роли инфраструктуры Windows (DNS, DHCP, DC, NTP, PRINT, файловый сервер, IAM и т. д.) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d439f-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="d439f-116">Дополнительные неподдерживаемые сценарии и запросы от сообщества см. на форуме UserVoice для контейнеров Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="d439f-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d439f-117">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="d439f-117">Additional resources</span></span>

- <span data-ttu-id="d439f-118">**Виртуальные машины и контейнеры в Azure**</span><span class="sxs-lookup"><span data-stu-id="d439f-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="d439f-119">[Назад](deploy-existing-net-apps-as-windows-containers.md)
> [Вперед](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="d439f-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
