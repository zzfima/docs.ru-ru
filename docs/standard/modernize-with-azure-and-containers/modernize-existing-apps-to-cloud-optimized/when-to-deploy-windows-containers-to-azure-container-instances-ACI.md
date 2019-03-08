---
title: Когда следует развертывать контейнеры Windows экземпляры контейнеров Azure (ACI)
description: Модернизация существующих приложений .NET с помощью облака Azure и Windows контейнерах | Когда следует развертывать контейнеры Windows экземпляры контейнеров Azure (ACI)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 03ee7c8b65e1a92dcc7fd40b44e9ba081f571487
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674410"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="fe3d9-103">Когда следует развертывать контейнеры Windows экземпляры контейнеров Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="fe3d9-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="fe3d9-104">Экземпляры контейнеров Azure ценностное предложение основной том, что вы можете сразу развертывать контейнеры к нему и отсутствие необходимости в поддержке этой среды, не нужно обновлять и исправлять базовой операционной системы или виртуальные машины, все является прозрачным, и вы просто развертываете контейнеры в готовые к использованию среду.</span><span class="sxs-lookup"><span data-stu-id="fe3d9-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="fe3d9-105">Причины и сценарии, когда требуется использовать ACI похожи на основные сценарии при использовании виртуальных машин Azure с контейнерами, по сути, основные сценарии с помощью экземпляров контейнеров Azure:</span><span class="sxs-lookup"><span data-stu-id="fe3d9-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="fe3d9-106">**Сценарии разработки и тестирования**</span><span class="sxs-lookup"><span data-stu-id="fe3d9-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="fe3d9-107">**Автоматизация задач**</span><span class="sxs-lookup"><span data-stu-id="fe3d9-107">**Task automation**</span></span>
- <span data-ttu-id="fe3d9-108">**Непрерывная Интеграция и развертывание агентов**</span><span class="sxs-lookup"><span data-stu-id="fe3d9-108">**CI/CD agents**</span></span>
- <span data-ttu-id="fe3d9-109">**Малый или масштабом пакетной обработки**</span><span class="sxs-lookup"><span data-stu-id="fe3d9-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="fe3d9-110">**Простой веб-приложений**</span><span class="sxs-lookup"><span data-stu-id="fe3d9-110">**Simple web apps**</span></span>

<span data-ttu-id="fe3d9-111">Простой веб-приложений сценарий это справедливого сценарий для ACI, но принимать во внимание, что так как в экземпляре контейнера AZURE может иметь только экземпляр один контейнер на образ контейнера, не будут иметь высокий уровень доступности и иметь только ограниченные масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="fe3d9-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="fe3d9-112">Однако даже в том случае, если ACI считается инфраструктуры, так как она просто предоставляет экземпляры одного контейнера, то есть огромным преимуществом по сравнению с обычными виртуальными машинами Azure с помощью Windows Server.</span><span class="sxs-lookup"><span data-stu-id="fe3d9-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="fe3d9-113">Экземпляры контейнеров Azure вы просто развертываете контейнеры в среде самостоятельно сохраняются, и вы просто платите за этими контейнерами.</span><span class="sxs-lookup"><span data-stu-id="fe3d9-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="fe3d9-114">Не нужно поддерживать/обновлений и исправлений виртуальных машин, так что это более эффективную платформу для большинства сценариев, где возможно, вы используете виртуальные машины с контейнерами.</span><span class="sxs-lookup"><span data-stu-id="fe3d9-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="fe3d9-115">С помощью ACI выполняется очень легко, просто разверните контейнер, нет необходимости, чтобы создать среду виртуальных Машин, вы просто развертываете контейнеры.</span><span class="sxs-lookup"><span data-stu-id="fe3d9-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="fe3d9-116">Являются основными преимуществами экземпляры контейнеров Azure (ACI):</span><span class="sxs-lookup"><span data-stu-id="fe3d9-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="fe3d9-117">Запуск контейнеров без управления серверами</span><span class="sxs-lookup"><span data-stu-id="fe3d9-117">Run containers without managing servers</span></span>
- <span data-ttu-id="fe3d9-118">Повышение гибкости с использованием контейнеров по запросу</span><span class="sxs-lookup"><span data-stu-id="fe3d9-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="fe3d9-119">Развертывание контейнеров в облаке с непревзойденной простотой и скоростью, с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="fe3d9-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="fe3d9-120">Обеспечение безопасности приложений благодаря изоляции гипервизора</span><span class="sxs-lookup"><span data-stu-id="fe3d9-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="fe3d9-121">Иными словами экземпляры контейнеров Azure вы можете разрабатывать приложения быстро без управления виртуальными машинами или изучения новых средств.</span><span class="sxs-lookup"><span data-stu-id="fe3d9-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="fe3d9-122">Это просто ваше приложение в контейнере, запущенном в облаке.</span><span class="sxs-lookup"><span data-stu-id="fe3d9-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="fe3d9-123">[Назад](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Вперед](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="fe3d9-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
