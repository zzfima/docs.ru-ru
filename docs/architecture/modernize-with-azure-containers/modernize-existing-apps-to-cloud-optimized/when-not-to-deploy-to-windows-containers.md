---
title: Технологии, не поддерживающие развертывание в контейнерах Windows
description: Модернизация существующих приложений .NET с помощью облака Azure и контейнеров Windows | Технологии, не поддерживающие развертывание в контейнерах Windows
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577957"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="89693-103">Технологии, не поддерживающие развертывание в контейнерах Windows</span><span class="sxs-lookup"><span data-stu-id="89693-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="89693-104">Некоторые технологии Windows не поддерживаются контейнерами Windows.</span><span class="sxs-lookup"><span data-stu-id="89693-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="89693-105">В таких случаях вам по-прежнему нужно выполнить миграцию на стандартные виртуальные машины, обычно с использованием только Windows и IIS.</span><span class="sxs-lookup"><span data-stu-id="89693-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="89693-106">Сценарии, не поддерживающиеся в контейнерах Windows по состоянию на май 2018 года:</span><span class="sxs-lookup"><span data-stu-id="89693-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="89693-107">В настоящее время технология очередей сообщений (MSMQ) доступна только в контейнерах Windows с выпуском Windows Server версии 1803, но не с предыдущими выпусками.</span><span class="sxs-lookup"><span data-stu-id="89693-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="89693-108">Форум по запросам UserVoice</span><span class="sxs-lookup"><span data-stu-id="89693-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="89693-109">Форум обсуждения</span><span class="sxs-lookup"><span data-stu-id="89693-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="89693-110">Координатор распределенных транзакций Майкрософт (MSDTC) в настоящее время не поддерживается в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="89693-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="89693-111">Проблема, рассмотренная на сайте GitHub</span><span class="sxs-lookup"><span data-stu-id="89693-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="89693-112">Microsoft Office в настоящее время не поддерживает контейнеры.</span><span class="sxs-lookup"><span data-stu-id="89693-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="89693-113">Форум по запросам UserVoice</span><span class="sxs-lookup"><span data-stu-id="89693-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="89693-114">Приложения пользовательского интерфейса (клиентские приложения с визуальным пользовательским интерфейсом) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="89693-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="89693-115">Роли инфраструктуры Windows (DNS, DHCP, DC, NTP, PRINT, файловый сервер, IAM и т. д.) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="89693-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="89693-116">Дополнительные неподдерживаемые сценарии и запросы от сообщества см. в разделе форума UserVoice, посвященном контейнерам Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="89693-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="89693-117">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="89693-117">Additional resources</span></span>

- <span data-ttu-id="89693-118">**Виртуальные машины и контейнеры в Azure**</span><span class="sxs-lookup"><span data-stu-id="89693-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="89693-119">[Назад](deploy-existing-net-apps-as-windows-containers.md)
> [Вперед](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="89693-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
