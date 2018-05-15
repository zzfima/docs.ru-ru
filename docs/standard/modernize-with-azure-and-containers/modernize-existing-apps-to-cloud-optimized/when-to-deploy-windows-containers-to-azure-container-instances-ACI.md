---
title: Если развернуть контейнеры Windows в Azure контейнера экземпляров ACI
description: Модернизировать существующие приложения .NET с контейнерами Windows и облако Azure | Если развернуть контейнеры Windows в Azure контейнера экземпляров ACI
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 3dc23c96543d9611763b571105f52b150dfec06f
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="c69b2-103">Если развернуть контейнеры Windows в Azure контейнера экземпляров ACI</span><span class="sxs-lookup"><span data-stu-id="c69b2-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="c69b2-104">Экземпляры Azure контейнер является главной ценностное предложение, можно сразу развернуть контейнеры он и не требуется для поддержки этой среды, не требуется исправление или обновление базовые операционной системы или виртуальных машин, все, прозрачно и просто развертывания контейнеры в среду готовые к использованию.</span><span class="sxs-lookup"><span data-stu-id="c69b2-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlaying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="c69b2-105">Причины и сценарии, когда требуется использовать ACI похожи на основные сценарии при использовании виртуальных машин Azure с помощью контейнеров, по сути, являются основные сценарии для использования экземпляров контейнера Azure:</span><span class="sxs-lookup"><span data-stu-id="c69b2-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

-   <span data-ttu-id="c69b2-106">**Сценариев разработки и тестирования**</span><span class="sxs-lookup"><span data-stu-id="c69b2-106">**Dev/Test scenarios**</span></span>
-   <span data-ttu-id="c69b2-107">**Автоматизация задач**</span><span class="sxs-lookup"><span data-stu-id="c69b2-107">**Task automation**</span></span>
-   <span data-ttu-id="c69b2-108">**Агенты CI или компакт-диска**</span><span class="sxs-lookup"><span data-stu-id="c69b2-108">**CI/CD agents**</span></span>
-   <span data-ttu-id="c69b2-109">**Малый или шкала пакетной обработки**</span><span class="sxs-lookup"><span data-stu-id="c69b2-109">**Small/scale batch processing**</span></span>
-   <span data-ttu-id="c69b2-110">**Простой веб-приложений**</span><span class="sxs-lookup"><span data-stu-id="c69b2-110">**Simple web apps**</span></span>

<span data-ttu-id="c69b2-111">Простой веб-сценарий для приложения удовлетворительные сценарий для ACI но принимать во внимание, что поскольку ACI можно установить только один контейнер экземпляр на образ контейнера, не обеспечивают высокий уровень доступности и только ограниченной масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="c69b2-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="c69b2-112">Однако даже в том случае, если ACI считается инфраструктуры, так как он просто содержит экземпляры одного контейнера, то есть огромное преимущество по сравнению с регулярного виртуальные машины Azure с Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c69b2-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="c69b2-113">С ACI просто развернуть контейнеры в самостоятельно сохранять среды и вы платите только за такие контейнеры.</span><span class="sxs-lookup"><span data-stu-id="c69b2-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="c69b2-114">Нет необходимости обслуживания или обновления, исправления виртуальные машины, так что это гораздо более эффективную платформу для большинства сценариев, где возможно, вы используете виртуальные машины с помощью контейнеров.</span><span class="sxs-lookup"><span data-stu-id="c69b2-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="c69b2-115">С помощью ACI прост, вы просто развертывания контейнера, нет необходимости для создания виртуальной Машины среды, можно просто развернуть контейнеры.</span><span class="sxs-lookup"><span data-stu-id="c69b2-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="c69b2-116">Ниже перечислены преимущества основных экземпляры контейнером в Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="c69b2-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

-   <span data-ttu-id="c69b2-117">Запускать контейнеры без управления серверами</span><span class="sxs-lookup"><span data-stu-id="c69b2-117">Run containers without managing servers</span></span>
-   <span data-ttu-id="c69b2-118">Повышают гибкость с контейнерами по требованию</span><span class="sxs-lookup"><span data-stu-id="c69b2-118">Increase agility with containers on demand</span></span>
-   <span data-ttu-id="c69b2-119">Развертывание контейнеров в облако с Непревзойденная простота и скорость, с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="c69b2-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span> 
-   <span data-ttu-id="c69b2-120">Безопасность приложений с изоляцией низкоуровневой оболочки</span><span class="sxs-lookup"><span data-stu-id="c69b2-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="c69b2-121">Иными словами с ACI приложения можно разрабатывать быстро без управления виртуальными машинами и изучая новые средства.</span><span class="sxs-lookup"><span data-stu-id="c69b2-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="c69b2-122">Это только приложения, в контейнере, работающими в облаке.</span><span class="sxs-lookup"><span data-stu-id="c69b2-122">It's just your application, in a container, running in the cloud.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="c69b2-123">[Назад](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Вперед](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="c69b2-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
