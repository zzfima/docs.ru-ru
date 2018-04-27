---
title: Если для развертывания контейнеров Windows на виртуальных машинах Azure (IaaS облако)
description: Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Если для развертывания контейнеров Windows на виртуальных машинах Azure (IaaS облако)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d1a9f0593b4b84cbe25da9e4164f4ecbe8513831
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="55bbd-103">Если для развертывания контейнеров Windows на виртуальных машинах Azure (IaaS облако)</span><span class="sxs-lookup"><span data-stu-id="55bbd-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="55bbd-104">Если ваша организация использует Azure виртуальные машины, даже если используются контейнеры Windows, вы по-прежнему являются задействования IaaS.</span><span class="sxs-lookup"><span data-stu-id="55bbd-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="55bbd-105">Это означает, задействования операций инфраструктуры, исправлений ОС ВМ и сложность инфраструктуры для масштабируемых приложений, если необходимо выполнить развертывание на нескольких виртуальных машин в инфраструктуре балансировкой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="55bbd-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="55bbd-106">Ниже приведены основные сценарии с использованием контейнеров Windows на виртуальной Машине Azure.</span><span class="sxs-lookup"><span data-stu-id="55bbd-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

-   <span data-ttu-id="55bbd-107">**Среда разработки и тестирования**: виртуальной Машины в облаке идеально подходит для разработки и тестирования в облаке.</span><span class="sxs-lookup"><span data-stu-id="55bbd-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="55bbd-108">Можно быстро создать или остановка среды, в зависимости от потребностей.</span><span class="sxs-lookup"><span data-stu-id="55bbd-108">You can rapidly create or stop the environment depending on your needs.</span></span>

-   <span data-ttu-id="55bbd-109">**Требуется масштабируемость малых и средних**: В сценариях, где может понадобиться несколько виртуальных машин для рабочей среды, управлении небольшое количество виртуальных машин может быть доступной пока можно переместить в более сложных средах PaaS, например orchestrators.</span><span class="sxs-lookup"><span data-stu-id="55bbd-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

-   <span data-ttu-id="55bbd-110">**Рабочей среде с существующими средствами развертывания**: которые могут перемещаться из локальной среды, в которой были вложены в средствах для сложных развертываний виртуальных машин или новых серверов (например, Puppet или аналогичные средства).</span><span class="sxs-lookup"><span data-stu-id="55bbd-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="55bbd-111">Для перемещения в облако с минимальными изменениями в рабочей среде развертывания процедуры, могут продолжать использовать эти средства для развертывания на виртуальных машинах Azure.</span><span class="sxs-lookup"><span data-stu-id="55bbd-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="55bbd-112">Тем не менее может потребоваться использовать контейнеры Windows в качестве единицей развертывания улучшить процесс развертывания.</span><span class="sxs-lookup"><span data-stu-id="55bbd-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="55bbd-113">[Назад](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Вперед](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="55bbd-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
