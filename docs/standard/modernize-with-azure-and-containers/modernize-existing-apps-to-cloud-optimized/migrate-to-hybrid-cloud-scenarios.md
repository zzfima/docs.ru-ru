---
title: Переход на гибридные облачные сценарии
description: Модернизация существующих приложений .NET с помощью облака Azure и Windows контейнерах | Перенос в гибридных облачных сценариев
ms.date: 04/30/2018
ms.openlocfilehash: 04c618681c61f5584e641e0a4735e1261ab34fa3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643723"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="0d497-103">Переход на гибридные облачные сценарии</span><span class="sxs-lookup"><span data-stu-id="0d497-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="0d497-104">Некоторые компании и организации не удается выполнить миграцию некоторых приложений в общедоступные облака, такие как Microsoft Azure или любого другого общедоступного облака, из-за нормативы или свои собственные политики.</span><span class="sxs-lookup"><span data-stu-id="0d497-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="0d497-105">Тем не менее вполне вероятно, что любая организация может выиграть от необходимости некоторых приложений в общедоступном облаке и другие приложения на предприятии.</span><span class="sxs-lookup"><span data-stu-id="0d497-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="0d497-106">Но в смешанной среде может привести к чрезмерной сложности в средах, из-за различных платформ и технологий, используемых в общедоступных облаках и локальных сред.</span><span class="sxs-lookup"><span data-stu-id="0d497-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="0d497-107">Корпорация Майкрософт предоставляет лучшие гибридное Облачное решение, одно, в котором вы можете оптимизировать существующие ресурсы в локальной и в общедоступном облаке, обеспечить согласованность в гибридное облако Azure.</span><span class="sxs-lookup"><span data-stu-id="0d497-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="0d497-108">Можно развернуть имеющиеся навыки и получите гибкие унифицированные методы создания приложений, которые можно запускать в облаке или локально, благодаря Azure Stack (локальная) и Azure (общедоступное облако).</span><span class="sxs-lookup"><span data-stu-id="0d497-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="0d497-109">Что касается безопасности, можно централизовать управление и безопасность для гибридного облака.</span><span class="sxs-lookup"><span data-stu-id="0d497-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="0d497-110">Можно получить контроль над все ресурсы из вашего центра обработки данных в облако, предоставляя единый вход для локальных и облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="0d497-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="0d497-111">Это сделать путем расширения Active Directory в гибридное облако и с помощью управления удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="0d497-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="0d497-112">Наконец можно распространять и легко анализировать данные, использовать те же языки запросов для облачных и локальных ресурсов и применяйте аналитику и глубокое обучение в Azure для улучшения анализа данных, независимо от их источника.</span><span class="sxs-lookup"><span data-stu-id="0d497-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="0d497-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="0d497-113">Azure Stack</span></span>

<span data-ttu-id="0d497-114">Azure Stack — это гибридная облачная платформа, позволяющая доставлять службы Azure из центра обработки данных вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0d497-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="0d497-115">Azure Stack предназначена для поддержки новых параметров для современных приложений в ключевых сценариях, таких как edge, неподключенный сред и отвечая определенным безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="0d497-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="0d497-116">Рис. 4-13 показан обзор преимуществ истинной гибридной облачной платформы, корпорация Майкрософт предлагает.</span><span class="sxs-lookup"><span data-stu-id="0d497-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Гибридная облачная платформа Майкрософт с помощью Azure Stack и Azure](./media/image13.jpg)

> <span data-ttu-id="0d497-118">**Рис. 4-13.**</span><span class="sxs-lookup"><span data-stu-id="0d497-118">**Figure 4-13.**</span></span> <span data-ttu-id="0d497-119">Гибридная облачная платформа Майкрософт с помощью Azure Stack и Azure</span><span class="sxs-lookup"><span data-stu-id="0d497-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="0d497-120">Azure Stack предлагается в двух вариантах развертывания, в соответствии с требованиями:</span><span class="sxs-lookup"><span data-stu-id="0d497-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="0d497-121">Интегрированные системы Azure Stack</span><span class="sxs-lookup"><span data-stu-id="0d497-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="0d497-122">Пакет средств разработки Azure Stack</span><span class="sxs-lookup"><span data-stu-id="0d497-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="0d497-123">Интегрированные системы Azure Stack</span><span class="sxs-lookup"><span data-stu-id="0d497-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="0d497-124">Интегрированные системы Azure Stack предоставляются благодаря партнерским отношениям партнеров корпорации Майкрософт и оборудования.</span><span class="sxs-lookup"><span data-stu-id="0d497-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="0d497-125">Партнерство создает решение, позволяющее пошаговый метод облачных инновациях, которые балансируется с простотой управления.</span><span class="sxs-lookup"><span data-stu-id="0d497-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="0d497-126">Поскольку Azure Stack предлагается в виде интегрированной системы оборудования и программного обеспечения, вы получаете необходимой степенью гибкости и контроля, при этом адаптировать инновации из облака.</span><span class="sxs-lookup"><span data-stu-id="0d497-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="0d497-127">Интегрированные системы Azure Stack размер варьируется от 4 на 12 узлы и совместно поддерживаются партнером оборудования и корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0d497-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="0d497-128">Используйте интегрированных систем Azure Stack, чтобы реализовать новые сценарии для рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="0d497-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="0d497-129">Пакет средств разработки Azure Stack</span><span class="sxs-lookup"><span data-stu-id="0d497-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="0d497-130">Средств разработки Azure Stack — это развертывание одного узла Azure Stack, который можно использовать для оценки и изучения Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="0d497-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="0d497-131">Пакет средств разработки Azure Stack также можно использовать как среду разработки, где можно разрабатывать с помощью интерфейсов API и средства, которые согласованы с Azure.</span><span class="sxs-lookup"><span data-stu-id="0d497-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="0d497-132">Пакет средств разработки Azure Stack не предназначен для использования в качестве рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="0d497-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0d497-133">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="0d497-133">Additional resources</span></span>

- <span data-ttu-id="0d497-134">**Гибридное облако Azure**</span><span class="sxs-lookup"><span data-stu-id="0d497-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="0d497-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="0d497-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="0d497-136">**Учетные записи служб Active Directory для контейнеров Windows**</span><span class="sxs-lookup"><span data-stu-id="0d497-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="0d497-137">**Создайте контейнер с поддержкой Active Directory**</span><span class="sxs-lookup"><span data-stu-id="0d497-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="0d497-138">**Лицензирование Преимущество гибридного использования Azure**</span><span class="sxs-lookup"><span data-stu-id="0d497-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="0d497-139">[Назад](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Вперед](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0d497-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
