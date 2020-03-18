---
title: Переход на гибридные облачные сценарии
description: Модернизация существующих приложений .NET с помощью облака Azure и контейнеров Windows | Переход на гибридные облачные сценарии
ms.date: 04/30/2018
ms.openlocfilehash: dcbb799a45609f8bb811866c4041951abf1fda8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937366"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="1ba74-103">Переход на гибридные облачные сценарии</span><span class="sxs-lookup"><span data-stu-id="1ba74-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="1ba74-104">Некоторые организации и предприятия не могут перенести некоторые из своих приложений в общедоступные облака, такие как Microsoft Azure или любое другое, из-за нормативных требований или собственных политик.</span><span class="sxs-lookup"><span data-stu-id="1ba74-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="1ba74-105">Тем не менее, вполне вероятно, что любой организации может быть выгодно использовать некоторые приложения в общедоступном облаке, а некоторые — в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="1ba74-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="1ba74-106">Однако смешанная среда может привести к чрезмерной сложности из-за различных платформ и технологий, используемых в общедоступных облаках и локальных средах.</span><span class="sxs-lookup"><span data-stu-id="1ba74-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="1ba74-107">Корпорация Майкрософт предоставляет лучшее гибридное облачное решение, позволяющее оптимизировать существующие ресурсы локально и в общедоступном облаке, обеспечивая согласованность в гибридном облаке Azure.</span><span class="sxs-lookup"><span data-stu-id="1ba74-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="1ba74-108">Вы можете расширить имеющиеся навыки и получить гибкий унифицированный подход к сборке приложений, которые могут работать в облаке или локальной среде, благодаря Azure Stack (в локальной среде) и службе Azure (в общедоступном облаке).</span><span class="sxs-lookup"><span data-stu-id="1ba74-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="1ba74-109">Когда речь заходит о безопасности, вы можете централизовать управление и обеспечение безопасности в гибридном облаке.</span><span class="sxs-lookup"><span data-stu-id="1ba74-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="1ba74-110">Вы можете получить контроль над всеми ресурсами (от центра обработки данных до облака), реализовав единый вход в локальные и облачные приложения.</span><span class="sxs-lookup"><span data-stu-id="1ba74-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="1ba74-111">Это достигается путем расширения Active Directory в гибридное облако и управления идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="1ba74-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="1ba74-112">Наконец, вы можете легко распространять и анализировать данные, использовать одни и те же языки запросов для облачных и локальных ресурсов, а также применять аналитику и глубокое обучение в Azure для дополнения ваших данных независимо от их источника.</span><span class="sxs-lookup"><span data-stu-id="1ba74-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="1ba74-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="1ba74-113">Azure Stack</span></span>

<span data-ttu-id="1ba74-114">Azure Stack — это гибридная облачная платформа, которая позволяет доставлять службы Azure из корпоративного центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="1ba74-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="1ba74-115">Платформа Azure Stack предназначена для поддержки новых возможностей для современных приложений в ключевых сценариях, таких как пограничные и отключенные среды, или для соответствия определенным требованиям безопасности и законодательства.</span><span class="sxs-lookup"><span data-stu-id="1ba74-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="1ba74-116">На рис. 4-13 показан обзор реальной гибридной облачной платформы, предоставляемой корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1ba74-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Схема гибридной облачной платформы Майкрософт с Azure Stack и Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="1ba74-118">**Рис. 4-13.**</span><span class="sxs-lookup"><span data-stu-id="1ba74-118">**Figure 4-13.**</span></span> <span data-ttu-id="1ba74-119">Гибридная облачная платформа Майкрософт с Azure Stack и Azure</span><span class="sxs-lookup"><span data-stu-id="1ba74-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="1ba74-120">Для соответствия вашим потребностям Azure Stack предлагается в двух вариантах развертывания:</span><span class="sxs-lookup"><span data-stu-id="1ba74-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="1ba74-121">Интегрированные системы Azure Stack</span><span class="sxs-lookup"><span data-stu-id="1ba74-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="1ba74-122">Пакет средств разработки Azure Stack</span><span class="sxs-lookup"><span data-stu-id="1ba74-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="1ba74-123">Интегрированные системы Azure Stack</span><span class="sxs-lookup"><span data-stu-id="1ba74-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="1ba74-124">Интегрированные системы Azure Stack предлагаются благодаря партнерству корпорации Майкрософт с партнерами по оборудованию.</span><span class="sxs-lookup"><span data-stu-id="1ba74-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="1ba74-125">Это партнерство позволило создать решение, которое предлагает облачные инновации в сочетании с простотой управления.</span><span class="sxs-lookup"><span data-stu-id="1ba74-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="1ba74-126">Так как Azure Stack предлагается в форме интегрированной системы с программным и аппаратным обеспечением, вы получаете необходимый уровень гибкости и контроля, поддерживающий внедрение инноваций на базе облака.</span><span class="sxs-lookup"><span data-stu-id="1ba74-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="1ba74-127">Размер интегрированных систем Azure Stack варьируется от 4 до 12 узлов. Эти системы поддерживаются партнером по оборудованию и корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1ba74-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="1ba74-128">Использование интегрированных систем Azure Stack позволяет реализовать новые сценарии рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="1ba74-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="1ba74-129">Пакет средств разработки Azure Stack</span><span class="sxs-lookup"><span data-stu-id="1ba74-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="1ba74-130">Пакет средств разработки Azure Stack — это развертывание Azure Stack с одним узлом, удобное для оценки и изучения Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="1ba74-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="1ba74-131">Кроме того, Пакет средств разработки Azure Stack можно использовать как среду разработки, в которой можно разрабатывать решения с помощью API-интерфейсов и инструментов, совместимых с Azure.</span><span class="sxs-lookup"><span data-stu-id="1ba74-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="1ba74-132">Пакет средств разработки Azure Stack не предназначен для использования в качестве производственной среды.</span><span class="sxs-lookup"><span data-stu-id="1ba74-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1ba74-133">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="1ba74-133">Additional resources</span></span>

- <span data-ttu-id="1ba74-134">**Гибридное облако Azure**</span><span class="sxs-lookup"><span data-stu-id="1ba74-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="1ba74-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="1ba74-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="1ba74-136">**Учетные записи службы Active Directory для контейнеров Windows**</span><span class="sxs-lookup"><span data-stu-id="1ba74-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="1ba74-137">**Создание контейнера с поддержкой Active Directory**</span><span class="sxs-lookup"><span data-stu-id="1ba74-137">**Create a container with Active Directory support**</span></span>

    <https://docs.microsoft.com/archive/blogs/containerstuff/create-a-container-with-active-directory-support>

- <span data-ttu-id="1ba74-138">**Лицензия по программе "Преимущество гибридного использования Azure"**</span><span class="sxs-lookup"><span data-stu-id="1ba74-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="1ba74-139">[Назад](life-cycle-ci-cd-pipelines-devops-tools.md)
>[Вперед](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1ba74-139">[Previous](life-cycle-ci-cd-pipelines-devops-tools.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
