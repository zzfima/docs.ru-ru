---
title: "Когда не следует развернуть контейнеры Windows"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Когда не следует развернуть контейнеры Windows"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 538cb518cd169f42b3e8b7324ca108a1d366137a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="15410-103">Когда не следует развернуть контейнеры Windows</span><span class="sxs-lookup"><span data-stu-id="15410-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="15410-104">Некоторые технологии Windows не поддерживаются в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="15410-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="15410-105">В таких случаях необходимо для миграции виртуальных машин стандартов, обычно с просто Windows и служб IIS.</span><span class="sxs-lookup"><span data-stu-id="15410-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="15410-106">Случаи, не поддерживается в контейнерах Windows, начиная с mid 2017 г.:</span><span class="sxs-lookup"><span data-stu-id="15410-106">Cases not supported in Windows Containers, as of mid-2017:</span></span>

-   <span data-ttu-id="15410-107">Очередь сообщений (MSMQ) в настоящее время не поддерживается в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="15410-107">Microsoft Message Queuing (MSMQ) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="15410-108">Форум по запросу UserVoice</span><span class="sxs-lookup"><span data-stu-id="15410-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="15410-109">Дискуссионный форум</span><span class="sxs-lookup"><span data-stu-id="15410-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="15410-110">Координатор распределенных транзакций (MSDTC) в настоящее время не поддерживается в контейнерах Windows</span><span class="sxs-lookup"><span data-stu-id="15410-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers</span></span>

    -   [<span data-ttu-id="15410-111">Проблема GitHub</span><span class="sxs-lookup"><span data-stu-id="15410-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="15410-112">Microsoft Office в настоящее время не поддерживает контейнеры</span><span class="sxs-lookup"><span data-stu-id="15410-112">Microsoft Office currently does not support containers</span></span>

    -   [<span data-ttu-id="15410-113">Форум по запросу UserVoice</span><span class="sxs-lookup"><span data-stu-id="15410-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

<span data-ttu-id="15410-114">Дополнительные сценарии не поддерживаются и запросы от сообщества см. на форуме UserVoice для контейнеров Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="15410-114">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="15410-115">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="15410-115">Additional resources</span></span>

-   <span data-ttu-id="15410-116">**Виртуальные машины и контейнеры в Azure**</span><span class="sxs-lookup"><span data-stu-id="15410-116">**Virtual machines and containers in Azure**</span></span>

    [<span data-ttu-id="15410-117">https://docs.Microsoft.com/Azure/Virtual-Machines/Windows/Containers</span><span class="sxs-lookup"><span data-stu-id="15410-117">https://docs.microsoft.com/azure/virtual-machines/windows/containers</span></span>](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="15410-118">[Назад](deploy-existing-net-apps-as-windows-containers.md)
[Вперед](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="15410-118">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
