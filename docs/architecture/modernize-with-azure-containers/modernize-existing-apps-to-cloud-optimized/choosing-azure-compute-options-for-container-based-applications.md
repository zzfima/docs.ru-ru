---
title: Выбор вычислительных платформ Azure для контейнерных приложений
description: Модернизация существующих приложений .NET с помощью облака Azure и контейнеров Windows | Выбор вычислительных платформ Azure для контейнерных приложений
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "73736997"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="d5f1d-103">Выбор вычислительных платформ Azure для контейнерных приложений</span><span class="sxs-lookup"><span data-stu-id="d5f1d-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="d5f1d-104">Как вы заметили после ознакомления с предыдущими разделами, Azure — это открытое облако, предлагающее различные варианты.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="d5f1d-105">Вы можете подобрать самый подходящий для ваших нужд, но вам также нужно будет выбрать продукты или технологии, которые следует использовать для контейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="d5f1d-106">Ниже приведены основные критерии, по которым *рекомендуется* выбирать подходящее решение.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="d5f1d-107">**Единое монолитное приложение.** Выбор службы приложений Azure</span><span class="sxs-lookup"><span data-stu-id="d5f1d-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="d5f1d-108">**N-уровневое приложение.** Выберите такие оркестрации, как Служба Azure Kubernetes (AKS) или Служба приложений, если у вас одна или несколько серверных служб.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS) or App Service if you have a single or a few back-end services</span></span>
- <span data-ttu-id="d5f1d-109">**Микрослужбы.** Выберите AKS или Веб-приложения Azure для контейнеров.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="d5f1d-110">**Бессерверные функции и обработчики событий.** Выберите Функции Azure.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="d5f1d-111">**Широкомасштабная пакетная обработка.** Выберите пакетную службу Azure.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="d5f1d-112">Однако не следует слепо следовать этой рекомендации, так как выбор продукта зависит от потребностей и характеристик конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-112">However, this recommendation should be taken with a pinch of salt, as the product's selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="d5f1d-113">Не все приложения одинаковы, даже если изначально они могут выглядеть похожими.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="d5f1d-114">После углубленного анализа потребностей приложения изначальный и конечный выбранные продукты могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="d5f1d-115">Но в качестве отправной точки полезно иметь начальные рекомендации относительно того, где можно начать оценку и тестирование в зависимости от определенного приоритета.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="d5f1d-116">На рис. 1 различные виды приложений сопоставлены с их идеальными сценариями размещения в Azure.</span><span class="sxs-lookup"><span data-stu-id="d5f1d-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![Таблица, в которой показаны сценарии размещения Azure, подходящие для различных приложений.](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> <span data-ttu-id="d5f1d-118">[Назад](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Вперед](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="d5f1d-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
