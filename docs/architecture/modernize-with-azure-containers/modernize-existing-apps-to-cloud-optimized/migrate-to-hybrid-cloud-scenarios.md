---
title: Переход на гибридные облачные сценарии
description: Модернизировать существующих приложений .NET с помощью Azure Cloud and Windows Containers | Миграция в гибридные облачные сценарии
ms.date: 04/30/2018
ms.openlocfilehash: 4348a9b538042fee7ebd9c08f480491f17425937
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394544"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="408a4-103">Переход на гибридные облачные сценарии</span><span class="sxs-lookup"><span data-stu-id="408a4-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="408a4-104">Некоторые организации и предприятия не могут перенести некоторые из своих приложений в общедоступные облака, такие как Microsoft Azure или любое другое общедоступное облако из-за нормативных требований или их собственных политик.</span><span class="sxs-lookup"><span data-stu-id="408a4-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="408a4-105">Тем не менее, вполне вероятно, что любой организации может быть выгодно использовать некоторые приложения в общедоступном облаке и других приложениях в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="408a4-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="408a4-106">Однако смешанная среда может привести к чрезмерной сложности сред из-за различных платформ и технологий, используемых в общедоступных облаках и локальных средах.</span><span class="sxs-lookup"><span data-stu-id="408a4-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="408a4-107">Корпорация Майкрософт предоставляет лучшее гибридное облачное решение, позволяющее оптимизировать существующие ресурсы локально и в общедоступном облаке, обеспечивая согласованность в гибридном облаке Azure.</span><span class="sxs-lookup"><span data-stu-id="408a4-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="408a4-108">Вы можете максимально увеличить имеющиеся навыки и получить гибкий унифицированный подход к созданию приложений, которые могут работать в облаке или локальной среде, благодаря Azure Stack (в локальной среде) и Azure (общедоступное облако).</span><span class="sxs-lookup"><span data-stu-id="408a4-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="408a4-109">Когда речь заходит о безопасности, вы можете централизовать управление и безопасность в гибридном облаке.</span><span class="sxs-lookup"><span data-stu-id="408a4-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="408a4-110">Вы можете получить контроль над всеми ресурсами из центра обработки данных в облаке, предоставив единый вход в локальные и облачные приложения.</span><span class="sxs-lookup"><span data-stu-id="408a4-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="408a4-111">Это достигается путем расширения Active Directory в гибридное облако и с помощью управления удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="408a4-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="408a4-112">Наконец, вы можете легко распространять и анализировать данные, использовать одни и те же языки запросов для облачных и локальных ресурсов, а также применять аналитику и глубокое обучение в Azure для дополнения ваших данных независимо от их источника.</span><span class="sxs-lookup"><span data-stu-id="408a4-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="408a4-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="408a4-113">Azure Stack</span></span>

<span data-ttu-id="408a4-114">Azure Stack — это гибридная облачная платформа, которая позволяет предоставлять службы Azure из центра обработки данных Организации.</span><span class="sxs-lookup"><span data-stu-id="408a4-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="408a4-115">Azure Stack предназначен для поддержки новых возможностей современных приложений в ключевых сценариях, таких как пограничные и неподключенные среды, а также для удовлетворения конкретных требований к безопасности и соответствию.</span><span class="sxs-lookup"><span data-stu-id="408a4-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="408a4-116">На рис. 4-13 показан обзор реальной гибридной облачной платформы, предоставляемой корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="408a4-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Схема гибридной облачной платформы Майкрософт с Azure Stack и Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="408a4-118">**Рис. 4-13.**</span><span class="sxs-lookup"><span data-stu-id="408a4-118">**Figure 4-13.**</span></span> <span data-ttu-id="408a4-119">Гибридная облачная платформа Майкрософт с Azure Stack и Azure</span><span class="sxs-lookup"><span data-stu-id="408a4-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="408a4-120">Azure Stack предлагается в двух вариантах развертывания в соответствии с вашими потребностями:</span><span class="sxs-lookup"><span data-stu-id="408a4-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="408a4-121">Azure Stack интегрированные системы</span><span class="sxs-lookup"><span data-stu-id="408a4-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="408a4-122">Пакет средств разработки Azure Stack</span><span class="sxs-lookup"><span data-stu-id="408a4-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="408a4-123">Azure Stack интегрированные системы</span><span class="sxs-lookup"><span data-stu-id="408a4-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="408a4-124">Azure Stack интегрированные системы предоставляются через партнерство партнеров корпорации Майкрософт и оборудования.</span><span class="sxs-lookup"><span data-stu-id="408a4-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="408a4-125">Партнерство создает решение, которое предлагает инновации в облаке, которые сбалансированы с простотой управления.</span><span class="sxs-lookup"><span data-stu-id="408a4-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="408a4-126">Поскольку Azure Stack предлагается как интегрированная система оборудования и программного обеспечения, вы получаете правильный уровень гибкости и контроля, сохраняя инновации в облаке.</span><span class="sxs-lookup"><span data-stu-id="408a4-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="408a4-127">Azure Stack интегрированные системы имеют размер от 4 до 12 узлов и совместно поддерживаются партнером по оборудованию и корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="408a4-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="408a4-128">Используйте Azure Stack интегрированные системы для реализации новых сценариев для рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="408a4-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="408a4-129">Пакет средств разработки Azure Stack</span><span class="sxs-lookup"><span data-stu-id="408a4-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="408a4-130">Пакет средств разработки Microsoft Azure Stack — это развертывание Azure Stack с одним узлом, которое можно использовать для ознакомления и изучения Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="408a4-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="408a4-131">Вы также можете использовать Пакет средств разработки Azure Stack в качестве среды разработки, где можно разрабатывать интерфейсы API и средства, совместимые с Azure.</span><span class="sxs-lookup"><span data-stu-id="408a4-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="408a4-132">Пакет средств разработки Azure Stack не предназначен для использования в качестве рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="408a4-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="408a4-133">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="408a4-133">Additional resources</span></span>

- <span data-ttu-id="408a4-134">**Гибридное облако Azure**</span><span class="sxs-lookup"><span data-stu-id="408a4-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="408a4-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="408a4-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="408a4-136">**Учетные записи служб Active Directory для контейнеров Windows**</span><span class="sxs-lookup"><span data-stu-id="408a4-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="408a4-137">**Создание контейнера с поддержкой Active Directory**</span><span class="sxs-lookup"><span data-stu-id="408a4-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="408a4-138">**Лицензирование Преимущество гибридного использования Azure**</span><span class="sxs-lookup"><span data-stu-id="408a4-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="408a4-139">[Назад](life-cycle-ci-cd-pipelines-devops-tools.md)
>[Вперед](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="408a4-139">[Previous](life-cycle-ci-cd-pipelines-devops-tools.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
