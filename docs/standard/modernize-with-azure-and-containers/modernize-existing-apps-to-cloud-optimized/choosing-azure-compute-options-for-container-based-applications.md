---
title: Выбор вычислительных платформ Azure для контейнерных приложений
description: Модернизация существующих приложений .NET с помощью облака Azure и Windows контейнерах | Выбор платформ вычислений Azure для приложений на основе контейнера
ms.date: 05/04/2018
ms.openlocfilehash: d91cd279402dc24beb5f766c06cb85ac8d74f482
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758828"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="35ce3-103">Выбор вычислительных платформ Azure для контейнерных приложений</span><span class="sxs-lookup"><span data-stu-id="35ce3-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="35ce3-104">Как вы могли заметить после прочтения в предыдущих разделах, Azure — это открытая облачная, который предлагает несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="35ce3-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="35ce3-105">Можно использовать лучше всего подходит для ваших потребностей, однако он также перехватывает вопросы о какие продукта или технологии, следует использовать для контейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="35ce3-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="35ce3-106">Как *по умолчанию* рекомендация, ниже приведен основной критерий рекомендациями, приведенными в этом руководстве:</span><span class="sxs-lookup"><span data-stu-id="35ce3-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="35ce3-107">**Одного монолитного приложения:** Выберите службу приложений Azure</span><span class="sxs-lookup"><span data-stu-id="35ce3-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="35ce3-108">**N-уровневого приложения:** Выберите оркестраторы, такие как служба Azure Kubernetes (AKS) или службы приложений, если у вас есть один или несколько серверных служб</span><span class="sxs-lookup"><span data-stu-id="35ce3-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="35ce3-109">**Микрослужбы Linux:** Выберите AKS и Kubernetes</span><span class="sxs-lookup"><span data-stu-id="35ce3-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="35ce3-110">**Микрослужбы Windows:** Выбор веб-приложения Azure для контейнеров</span><span class="sxs-lookup"><span data-stu-id="35ce3-110">**Windows microservices:** Choose Azure Web Apps for Containers</span></span>
- <span data-ttu-id="35ce3-111">**Бессерверные функции & обработчики событий:** Выбор функций Azure</span><span class="sxs-lookup"><span data-stu-id="35ce3-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="35ce3-112">**Широкомасштабную пакетную:** Выберите пакетная служба Azure</span><span class="sxs-lookup"><span data-stu-id="35ce3-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="35ce3-113">Тем не менее Эта рекомендация должна применяться с жестом сжатия соли, как выбор продуктов будет зависеть от потребностей и характеристик конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="35ce3-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="35ce3-114">Не все приложения являются одинаковыми, даже в том случае, если изначально они выглядят сходных типов.</span><span class="sxs-lookup"><span data-stu-id="35ce3-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="35ce3-115">После более глубокого анализа потребностей приложения может отличаться выбранный продукт.</span><span class="sxs-lookup"><span data-stu-id="35ce3-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="35ce3-116">Качестве отправной точки, она хорошо иметь первоначальные инструкции, из которых можно приступить к оценке и тестировании, основанном на определенных приоритет.</span><span class="sxs-lookup"><span data-stu-id="35ce3-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="35ce3-117">На следующем рисунке вы увидите подробные сведения о различных типов приложений и их Azure идеально, сценарии размещения.</span><span class="sxs-lookup"><span data-stu-id="35ce3-117">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="35ce3-118">[Назад](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Вперед](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="35ce3-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
