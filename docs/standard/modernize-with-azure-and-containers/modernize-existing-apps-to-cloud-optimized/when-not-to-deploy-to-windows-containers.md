---
title: Когда не следует развертывать контейнеры Windows в
description: Модернизация существующих приложений .NET с помощью облака Azure и Windows контейнерах | Когда не следует развертывать контейнеры Windows в
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 940e94b45dcfb4e301b095cbe4ef5bcaf6752c4c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129900"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="806f1-103">Когда не следует развертывать контейнеры Windows в</span><span class="sxs-lookup"><span data-stu-id="806f1-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="806f1-104">Некоторые технологии Windows не поддерживаются в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="806f1-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="806f1-105">В таком случае необходимо перенести на виртуальные машины стандартов, обычно с помощью только Windows и IIS.</span><span class="sxs-lookup"><span data-stu-id="806f1-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="806f1-106">Случаи, не поддерживается в контейнерах Windows, по состоянию на май 2018 г.:</span><span class="sxs-lookup"><span data-stu-id="806f1-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="806f1-107">Очереди сообщений (Майкрософт) в настоящее время доступна только в зависимости от версии Windows Server v1803 контейнерах Windows, но не в предыдущих выпусках.</span><span class="sxs-lookup"><span data-stu-id="806f1-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="806f1-108">Запрос на форуме UserVoice</span><span class="sxs-lookup"><span data-stu-id="806f1-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="806f1-109">Дискуссионный форум</span><span class="sxs-lookup"><span data-stu-id="806f1-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="806f1-110">Координатор распределенных транзакций (MSDTC) в настоящее время не поддерживается в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="806f1-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="806f1-111">На сайте github</span><span class="sxs-lookup"><span data-stu-id="806f1-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="806f1-112">В настоящее время Microsoft Office не поддерживает контейнеры.</span><span class="sxs-lookup"><span data-stu-id="806f1-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="806f1-113">Запрос на форуме UserVoice</span><span class="sxs-lookup"><span data-stu-id="806f1-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="806f1-114">Пользовательский Интерфейс приложений (клиентских приложений с интерфейсом пользователя visual) не описаны поддерживаемые сценарии.</span><span class="sxs-lookup"><span data-stu-id="806f1-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="806f1-115">Инфраструктурные роли Windows (DNS, DHCP, Округ Колумбия, NTP, печати, файловый сервер, IAM и т.д.), не поддерживаемые сценарии.</span><span class="sxs-lookup"><span data-stu-id="806f1-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>


<span data-ttu-id="806f1-116">Дополнительные сценарии не поддерживаются и запросы от сообщества, см. на форуме UserVoice для контейнеров Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="806f1-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="806f1-117">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="806f1-117">Additional resources</span></span>

-   <span data-ttu-id="806f1-118">**Виртуальные машины и контейнеры в Azure**</span><span class="sxs-lookup"><span data-stu-id="806f1-118">**Virtual machines and containers in Azure**</span></span>

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
><span data-ttu-id="806f1-119">[Назад](deploy-existing-net-apps-as-windows-containers.md)
>[Вперед](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="806f1-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>