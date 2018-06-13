---
title: Выбор платформ вычислений Azure для приложений на основе контейнера
description: Модернизировать существующие приложения .NET с контейнерами Windows и облако Azure | Выбор платформ вычислений Azure для приложений на основе контейнера
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958014"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="2883a-103">Выбор платформ вычислений Azure для приложений на основе контейнера</span><span class="sxs-lookup"><span data-stu-id="2883a-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="2883a-104">Как вы заметили после считывания из предыдущих разделов, Azure — открыть облака, который предлагает несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="2883a-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="2883a-105">Можно использовать наилучшего соответствия вашим потребностям, однако он также предоставляет доступ к вопросы о какой продукта или технологии, следует использовать для приложений в контейнерах.</span><span class="sxs-lookup"><span data-stu-id="2883a-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="2883a-106">Как *по умолчанию* рекомендации, вот основные критерии рекомендациями, приведенными в этом руководстве:</span><span class="sxs-lookup"><span data-stu-id="2883a-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

  - <span data-ttu-id="2883a-107">**Одно приложение монолитные:** выберите службу приложений Azure</span><span class="sxs-lookup"><span data-stu-id="2883a-107">**Single monolithic app:** Choose Azure App Service</span></span>
  - <span data-ttu-id="2883a-108">**N-уровневого приложения:** orchestrators, например Kubernetes службы Azure (AKS), служба Fabric (SF) или службы приложения следует выбирать, если один или несколько служб,</span><span class="sxs-lookup"><span data-stu-id="2883a-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
  - <span data-ttu-id="2883a-109">**Микрослужбами Linux:** выберите AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="2883a-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
  - <span data-ttu-id="2883a-110">**Windows микрослужбами:** выберите Service Fabric</span><span class="sxs-lookup"><span data-stu-id="2883a-110">**Windows microservices:** Choose Service Fabric</span></span>
  - <span data-ttu-id="2883a-111">**Функции без сервера и обработчики событий:** выберите функций Azure</span><span class="sxs-lookup"><span data-stu-id="2883a-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
  - <span data-ttu-id="2883a-112">**Широкомасштабную пакетную:** выберите пакет Azure</span><span class="sxs-lookup"><span data-stu-id="2883a-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="2883a-113">Однако эта рекомендация должна быть принята с сжатие соли, как выбор продуктов будет зависеть от потребностей конкретного приложения и их характеристики.</span><span class="sxs-lookup"><span data-stu-id="2883a-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="2883a-114">Не все приложения будут такими же, даже в том случае, если изначально они выглядят сходных типов.</span><span class="sxs-lookup"><span data-stu-id="2883a-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="2883a-115">После более глубокого анализа потребностей приложения выбранный продукт может быть иным.</span><span class="sxs-lookup"><span data-stu-id="2883a-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="2883a-116">Однако отправной точки, хорошо иметь начальное руководство из которых можно начать ознакомление с и тестирование на основе определенных приоритета.</span><span class="sxs-lookup"><span data-stu-id="2883a-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="2883a-117">На следующем рисунке можно проанализировать более глобальный при таблицы подробные принятия решений.</span><span class="sxs-lookup"><span data-stu-id="2883a-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="2883a-118">Обратите внимание на то что базовой ОС (Windows vs. Linux) также может быть Коэффициент принятия решений, как некоторые orchestrators более зрелыми на контейнеры Linux и других в контейнерах Windows.</span><span class="sxs-lookup"><span data-stu-id="2883a-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="2883a-119">Например контейнеры Linux отличается высоким Kubernetes (AKS в Azure), но менее надежная на Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="2883a-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="2883a-120">С другой стороны контейнеры Windows — более развитым в Service Fabric (выпущенной в мае 2017 г.) и менее развитую в AKS.</span><span class="sxs-lookup"><span data-stu-id="2883a-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="2883a-121">Тем не менее, эти различия в зрелости ОС будет затухание в будущем и несколько платформ получат сопоставимых зрелости ОС и решение будет разместить несколько от выбранных параметров на основе определенных функций приложения может потребоваться или в зависимости от экосистемы каждой платформы причины.</span><span class="sxs-lookup"><span data-stu-id="2883a-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="2883a-122">[Назад](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Вперед](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="2883a-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
