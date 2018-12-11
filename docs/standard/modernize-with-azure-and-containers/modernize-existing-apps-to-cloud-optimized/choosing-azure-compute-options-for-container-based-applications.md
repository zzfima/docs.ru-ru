---
title: Выбор платформ вычислений Azure для приложений на основе контейнера
description: Модернизация существующих приложений .NET с помощью облака Azure и Windows контейнерах | Выбор платформ вычислений Azure для приложений на основе контейнера
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: 20d8899d404ec72e3b1b9c2471524133a6428c44
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125500"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="93386-103">Выбор платформ вычислений Azure для приложений на основе контейнера</span><span class="sxs-lookup"><span data-stu-id="93386-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="93386-104">Как вы могли заметить после прочтения в предыдущих разделах, Azure — это открытая облачная, который предлагает несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="93386-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="93386-105">Можно использовать лучше всего подходит для ваших потребностей, однако он также перехватывает вопросы о какие продукта или технологии, следует использовать для контейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="93386-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="93386-106">Как *по умолчанию* рекомендация, ниже приведен основной критерий рекомендациями, приведенными в этом руководстве:</span><span class="sxs-lookup"><span data-stu-id="93386-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

  - <span data-ttu-id="93386-107">**Одного монолитного приложения:** Выберите службу приложений Azure</span><span class="sxs-lookup"><span data-stu-id="93386-107">**Single monolithic app:** Choose Azure App Service</span></span>
  - <span data-ttu-id="93386-108">**N-уровневого приложения:** Выберите оркестраторы, такие как служба Azure Kubernetes (AKS), Service Fabric (SF) или службы приложений, если у вас есть один или несколько серверных служб</span><span class="sxs-lookup"><span data-stu-id="93386-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
  - <span data-ttu-id="93386-109">**Микрослужбы Linux:** Выберите AKS и Kubernetes</span><span class="sxs-lookup"><span data-stu-id="93386-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
  - <span data-ttu-id="93386-110">**Микрослужбы Windows:** Выберите Service Fabric</span><span class="sxs-lookup"><span data-stu-id="93386-110">**Windows microservices:** Choose Service Fabric</span></span>
  - <span data-ttu-id="93386-111">**Бессерверные функции & обработчики событий:** Выбор функций Azure</span><span class="sxs-lookup"><span data-stu-id="93386-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
  - <span data-ttu-id="93386-112">**Широкомасштабную пакетную:** Выберите пакетная служба Azure</span><span class="sxs-lookup"><span data-stu-id="93386-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="93386-113">Тем не менее Эта рекомендация должна применяться с жестом сжатия соли, как выбор продуктов будет зависеть от потребностей и характеристик конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="93386-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="93386-114">Не все приложения являются одинаковыми, даже в том случае, если изначально они выглядят сходных типов.</span><span class="sxs-lookup"><span data-stu-id="93386-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="93386-115">После более глубокого анализа потребностей приложения может отличаться выбранный продукт.</span><span class="sxs-lookup"><span data-stu-id="93386-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="93386-116">Качестве отправной точки, она хорошо иметь первоначальные инструкции, из которых можно приступить к оценке и тестировании, основанном на определенных приоритет.</span><span class="sxs-lookup"><span data-stu-id="93386-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="93386-117">На следующем рисунке можно проанализировать более глобальный при таблица подробные принятия решений.</span><span class="sxs-lookup"><span data-stu-id="93386-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="93386-118">Обратите внимание, что как основной операционной системы (Windows vs. Linux) также может быть фактору принятия решений, так как некоторые оркестраторы, более зрелой в контейнерах Linux и других в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="93386-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="93386-119">Например контейнеры Linux — очень зрелым в Kubernetes (AKS в Azure), но менее зрелым в Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="93386-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="93386-120">С другой стороны контейнеры Windows являются более зрелой в Service Fabric (выпущенной в мае 2017) и менее зрелым в AKS.</span><span class="sxs-lookup"><span data-stu-id="93386-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="93386-121">Тем не менее в будущем будет скрывать эти различия в ОС зрелости несколько платформ будет сопоставимых зрелости ОС и решение будет разместить дополнительные от выбранных параметров на основе определенных признаков, приложение может потребоваться или зависимости от экосистемы каждой платформы причины.</span><span class="sxs-lookup"><span data-stu-id="93386-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="93386-122">[Назад](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[Вперед](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="93386-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>