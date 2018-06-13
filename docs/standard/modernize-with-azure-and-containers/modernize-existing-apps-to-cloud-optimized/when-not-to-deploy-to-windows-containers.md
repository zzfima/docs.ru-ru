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
ms.locfileid: "33957964"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="a0809-103">Когда не следует развернуть контейнеры Windows</span><span class="sxs-lookup"><span data-stu-id="a0809-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="a0809-104">Некоторые технологии Windows не поддерживаются в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="a0809-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="a0809-105">В таких случаях необходимо для миграции виртуальных машин стандартов, обычно с просто Windows и служб IIS.</span><span class="sxs-lookup"><span data-stu-id="a0809-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="a0809-106">Не поддерживается в контейнерах Windows, по состоянию на май 2018 случаи:</span><span class="sxs-lookup"><span data-stu-id="a0809-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="a0809-107">Очередь сообщений (MSMQ) в настоящее время доступна только в зависимости от версии Windows Server v1803 контейнерах Windows, но не в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="a0809-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="a0809-108">Форум по запросу UserVoice</span><span class="sxs-lookup"><span data-stu-id="a0809-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="a0809-109">Дискуссионный форум</span><span class="sxs-lookup"><span data-stu-id="a0809-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="a0809-110">Координатор распределенных транзакций (MSDTC) в настоящее время не поддерживается в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="a0809-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="a0809-111">Проблема GitHub</span><span class="sxs-lookup"><span data-stu-id="a0809-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="a0809-112">В настоящее время Microsoft Office не поддерживает контейнеры.</span><span class="sxs-lookup"><span data-stu-id="a0809-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="a0809-113">Форум по запросу UserVoice</span><span class="sxs-lookup"><span data-stu-id="a0809-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="a0809-114">Пользовательский Интерфейс приложения (приложения для клиента с с графическим пользовательским интерфейсом), не поддерживаемые сценарии.</span><span class="sxs-lookup"><span data-stu-id="a0809-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="a0809-115">Роли Windows инфраструктуры (DNS, DHCP-, DC, NTP, печать, файловым сервером, IAM т. д.), не поддерживаемые сценарии.</span><span class="sxs-lookup"><span data-stu-id="a0809-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>


<span data-ttu-id="a0809-116">Дополнительные сценарии не поддерживаются и запросы от сообщества см. на форуме UserVoice для контейнеров Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="a0809-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a0809-117">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="a0809-117">Additional resources</span></span>

-   <span data-ttu-id="a0809-118">**Виртуальные машины и контейнеры в Azure**</span><span class="sxs-lookup"><span data-stu-id="a0809-118">**Virtual machines and containers in Azure**</span></span>

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="a0809-119">[Назад](deploy-existing-net-apps-as-windows-containers.md)
[Вперед](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="a0809-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
