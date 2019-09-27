---
title: Выбор вычислительных платформ Azure для контейнерных приложений
description: Модернизировать существующих приложений .NET с помощью Azure Cloud and Windows Containers | Выбор платформ вычислений Azure для приложений на основе контейнеров
ms.date: 05/04/2018
ms.openlocfilehash: 54c5945326fb8a50a39c50552a413580926da2c7
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71331960"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="11da4-103">Выбор вычислительных платформ Azure для контейнерных приложений</span><span class="sxs-lookup"><span data-stu-id="11da4-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="11da4-104">Как вы заметили после ознакомления с предыдущими разделами, Azure — это открытое облако, предлагающее несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="11da4-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="11da4-105">Вы можете использовать наиболее подходящие для ваших нужд, но в нем также будут выпадать вопросы о продукте или технологии, которые следует использовать для контейнерных приложений.</span><span class="sxs-lookup"><span data-stu-id="11da4-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="11da4-106">В качестве рекомендации по *умолчанию* ниже приведены основные критерии, Рекомендуемые в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="11da4-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="11da4-107">**Отдельное монолитное приложение:** Выберите службу приложений Azure</span><span class="sxs-lookup"><span data-stu-id="11da4-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="11da4-108">**N-уровневое приложение:** Выберите такие оркестрации, как служба Azure Kubernetes Service (AKS) или служба приложений, если у вас одна или несколько серверных служб.</span><span class="sxs-lookup"><span data-stu-id="11da4-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="11da4-109">**Микрослужб** Выбор AKS или веб-приложений Azure для контейнеров</span><span class="sxs-lookup"><span data-stu-id="11da4-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="11da4-110">**Бессерверные функции & обработчики событий:** Выбор функций Azure</span><span class="sxs-lookup"><span data-stu-id="11da4-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="11da4-111">**Пакет крупномасштабного масштабирования:** Выбор пакетной службы Azure</span><span class="sxs-lookup"><span data-stu-id="11da4-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="11da4-112">Однако эта рекомендация должна быть сделана с помощью сжатия Salt-файла, так как выбор продукта зависит от потребностей конкретного приложения и характеристик.</span><span class="sxs-lookup"><span data-stu-id="11da4-112">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="11da4-113">Не все приложения одинаковы, даже если изначально они могут выглядеть похожими типами.</span><span class="sxs-lookup"><span data-stu-id="11da4-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="11da4-114">После углубленного анализа потребностей приложения выбранный продукт может отличаться.</span><span class="sxs-lookup"><span data-stu-id="11da4-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="11da4-115">Но в качестве отправной точки полезно иметь начальные рекомендации от того, где можно начать оценку и тестирование на основе определенного приоритета.</span><span class="sxs-lookup"><span data-stu-id="11da4-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="11da4-116">На рис. 1 можно увидеть разделение различных видов приложений и их идеальные сценарии размещения Azure.</span><span class="sxs-lookup"><span data-stu-id="11da4-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![Рис. 1](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="11da4-118">[Назад](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Вперед](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="11da4-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
