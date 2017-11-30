---
title: "Перенос в гибридных облачных сценариев"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Перенос в гибридных облачных сценариев"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/2/2017
ms.openlocfilehash: 7394d0fd208e131b4e683298f6ca31a9eddade28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="2e1da-103">Перенос в гибридных облачных сценариев</span><span class="sxs-lookup"><span data-stu-id="2e1da-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="2e1da-104">В некоторых организациях и предприятий нельзя перенести некоторые свои приложения и общедоступных облаках, таких как Microsoft Azure или других общедоступных облаках из-за нормативов или собственные политики.</span><span class="sxs-lookup"><span data-stu-id="2e1da-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="2e1da-105">Тем не менее вероятнее всего, любой организации может выиграть от необходимости некоторые свои приложения в общедоступном облаке и другие приложения локально.</span><span class="sxs-lookup"><span data-stu-id="2e1da-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="2e1da-106">Но в смешанной среде может привести к чрезмерной сложности в средах из-за различных платформ и технологий, используемых в общедоступные облака и локальных средах.</span><span class="sxs-lookup"><span data-stu-id="2e1da-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="2e1da-107">Корпорация Майкрософт предоставляет наиболее гибридное Облачное решение, один оптимизировать активах существующих локальных и в общедоступном облаке, обеспечить согласованность в Azure гибридного облака.</span><span class="sxs-lookup"><span data-stu-id="2e1da-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="2e1da-108">Можно развернуть существующие навыки и получить гибкий и унифицированный способ создания приложений, которые могут выполняться в облаке или локально, благодаря Azure стека (локальной) и Azure (общедоступное облако).</span><span class="sxs-lookup"><span data-stu-id="2e1da-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="2e1da-109">Когда дело доходит до безопасности, управления и обеспечения безопасности можно централизовать через вашего гибридного облака.</span><span class="sxs-lookup"><span data-stu-id="2e1da-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="2e1da-110">Можно получить контроль над все ресурсы из центра обработки данных в облако, предоставляя единого входа в локальную среду и облачные приложения.</span><span class="sxs-lookup"><span data-stu-id="2e1da-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="2e1da-111">Это можно сделать путем расширения Active Directory для гибридного облака, а также с помощью диспетчера удостоверений.</span><span class="sxs-lookup"><span data-stu-id="2e1da-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="2e1da-112">И, наконец можно распространять и легко анализировать данные, использовать те же языки запросов для облачных и локальных средств и применить аналитики и глубокое изучение в Azure для обогащения данных, независимо от его источника.</span><span class="sxs-lookup"><span data-stu-id="2e1da-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="2e1da-113">Стек Azure</span><span class="sxs-lookup"><span data-stu-id="2e1da-113">Azure Stack</span></span>

<span data-ttu-id="2e1da-114">Стек Azure — гибридный облачная платформа, которая позволяет получать служб Azure из центра обработки данных вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2e1da-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="2e1da-115">Стек Azure предназначен для поддержки новых параметров для современных приложений в основные сценарии, например edge и изолированной среды или собрания безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="2e1da-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="2e1da-116">Рис. 4-13 приведен обзор true гибридной облачной платформы, корпорация Майкрософт предлагает.</span><span class="sxs-lookup"><span data-stu-id="2e1da-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Гибридные облачная платформа Майкрософт с помощью стека Azure и Azure](./media/image13.jpg)

> <span data-ttu-id="2e1da-118">**Рис. 4-13.**</span><span class="sxs-lookup"><span data-stu-id="2e1da-118">**Figure 4-13.**</span></span> <span data-ttu-id="2e1da-119">Гибридные облачная платформа Майкрософт с помощью стека Azure и Azure</span><span class="sxs-lookup"><span data-stu-id="2e1da-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="2e1da-120">Стек Azure доступна два варианта развертывания, чтобы соответствовать требованиям:</span><span class="sxs-lookup"><span data-stu-id="2e1da-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

-   <span data-ttu-id="2e1da-121">Стек Azure интегрированных систем</span><span class="sxs-lookup"><span data-stu-id="2e1da-121">Azure Stack integrated systems</span></span>

-   <span data-ttu-id="2e1da-122">Пакет средств разработки стек Azure</span><span class="sxs-lookup"><span data-stu-id="2e1da-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="2e1da-123">Стек Azure интегрированных систем</span><span class="sxs-lookup"><span data-stu-id="2e1da-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="2e1da-124">Azure стека интегрированных систем предоставляются в партнерстве партнеров Майкрософт и оборудования.</span><span class="sxs-lookup"><span data-stu-id="2e1da-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="2e1da-125">Партнерство создает решение, которое обеспечивает скорость облака инноваций, балансируется с простоты управления.</span><span class="sxs-lookup"><span data-stu-id="2e1da-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="2e1da-126">Так как стек Azure предлагается как интегрированной системой, программное обеспечение и оборудование, получении правильного объема гибкости и управляемости, во время по-прежнему внедрение инновационных из облака.</span><span class="sxs-lookup"><span data-stu-id="2e1da-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="2e1da-127">Azure стека интегрированных систем совместно поддерживаются партнера оборудования и корпорацией Майкрософт и диапазон размеру из 4 узлов 12.</span><span class="sxs-lookup"><span data-stu-id="2e1da-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="2e1da-128">Стек Azure используйте интегрированных систем для реализации новых сценариев для рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="2e1da-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="2e1da-129">Пакет средств разработки стек Azure</span><span class="sxs-lookup"><span data-stu-id="2e1da-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="2e1da-130">Пакет средств разработки Microsoft Azure стека — развертывание одного узла Azure стек, который можно использовать для оценки и Дополнительные сведения о стеке Azure.</span><span class="sxs-lookup"><span data-stu-id="2e1da-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="2e1da-131">Также можно использовать пакет средств разработки стек Azure как среды разработки, где можно разрабатывать с помощью интерфейсов API и средства, согласованные с Azure.</span><span class="sxs-lookup"><span data-stu-id="2e1da-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="2e1da-132">Пакет разработчика Azure стека не предназначен для использования в качестве рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="2e1da-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="2e1da-133">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="2e1da-133">Additional resources</span></span>

-   <span data-ttu-id="2e1da-134">**Azure гибридного облака**</span><span class="sxs-lookup"><span data-stu-id="2e1da-134">**Azure hybrid cloud**</span></span>

    [<span data-ttu-id="2e1da-135">https://www.Microsoft.com/Cloud-Platform/Hybrid-Cloud</span><span class="sxs-lookup"><span data-stu-id="2e1da-135">https://www.microsoft.com/cloud-platform/hybrid-cloud</span></span>](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   <span data-ttu-id="2e1da-136">**Стек Azure**</span><span class="sxs-lookup"><span data-stu-id="2e1da-136">**Azure Stack**</span></span>

    [<span data-ttu-id="2e1da-137">https://Azure.Microsoft.com/Overview/Azure-Stack/</span><span class="sxs-lookup"><span data-stu-id="2e1da-137">https://azure.microsoft.com/overview/azure-stack/</span></span>](https://azure.microsoft.com/overview/azure-stack/)

-   <span data-ttu-id="2e1da-138">**Учетные записи служб Active Directory для контейнеров Windows**</span><span class="sxs-lookup"><span data-stu-id="2e1da-138">**Active Directory Service Accounts for Windows Containers**</span></span>

    [<span data-ttu-id="2e1da-139">https://docs.Microsoft.com/Virtualization/windowscontainers/Manage-Containers/Manage-serviceaccounts</span><span class="sxs-lookup"><span data-stu-id="2e1da-139">https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   <span data-ttu-id="2e1da-140">**Создать контейнер с поддержкой Active Directory**</span><span class="sxs-lookup"><span data-stu-id="2e1da-140">**Create a container with Active Directory support**</span></span>

    [<span data-ttu-id="2e1da-141">https://blogs.MSDN.Microsoft.com/containerstuff/2017/01/30/Create-a-Container-WITH-Active-Directory-Support/</span><span class="sxs-lookup"><span data-stu-id="2e1da-141">https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/</span></span>](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   <span data-ttu-id="2e1da-142">**Лицензирование Azure Преимущество гибридного**</span><span class="sxs-lookup"><span data-stu-id="2e1da-142">**Azure Hybrid Benefit licensing**</span></span>

    [<span data-ttu-id="2e1da-143">https://Azure.Microsoft.com/Pricing/Hybrid-USE-Benefit/</span><span class="sxs-lookup"><span data-stu-id="2e1da-143">https://azure.microsoft.com/pricing/hybrid-use-benefit/</span></span>](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
<span data-ttu-id="2e1da-144">[Назад](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Вперед](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2e1da-144">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
