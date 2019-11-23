---
title: Устойчивость, ориентированная на облако
description: Создание архитектуры облачных приложений .NET для Azure | Устойчивость машинного кода в облаке
ms.date: 06/30/2019
ms.openlocfilehash: 680542abc5d8c43c577321d5ae834f0a13290da3
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841045"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="e6e03-103">Устойчивость, ориентированная на облако</span><span class="sxs-lookup"><span data-stu-id="e6e03-103">Cloud-native resiliency</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e6e03-104">Устойчивость — это способность системы реагировать на сбои и продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="e6e03-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="e6e03-105">Это не относится к предотвращению сбоев.</span><span class="sxs-lookup"><span data-stu-id="e6e03-105">It isn't about avoiding failure.</span></span> <span data-ttu-id="e6e03-106">Но в этом случае это неизбежно в облачных системах и построении приложения для реагирования на него.</span><span class="sxs-lookup"><span data-stu-id="e6e03-106">But it's about accepting that failure is inevitable in cloud-based systems and building your application to respond to it.</span></span> <span data-ttu-id="e6e03-107">Конечная цель обеспечения устойчивости — возврат приложения к полностью работоспособному состоянию после сбоя.</span><span class="sxs-lookup"><span data-stu-id="e6e03-107">The end-goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="e6e03-108">В отличие от традиционных монолитных приложений, где все работает вместе в одном процессе, облачные системы используют распределенную архитектуру, как показано на рисунке 6-1:</span><span class="sxs-lookup"><span data-stu-id="e6e03-108">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace distributed architecture as shown in Figure 6-1:</span></span>

![Распределенное облако — собственная среда](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="e6e03-110">**Рис. 6-1.**</span><span class="sxs-lookup"><span data-stu-id="e6e03-110">**Figure 6-1.**</span></span> <span data-ttu-id="e6e03-111">Распределенное облако — собственная среда</span><span class="sxs-lookup"><span data-stu-id="e6e03-111">Distributed cloud-native environment</span></span>

<span data-ttu-id="e6e03-112">На предыдущем рисунке обратите внимание, как каждый клиент, микрослужба и облачная [Служба резервного копирования](https://12factor.net/backing-services) выполняются как отдельный процесс, работающий на разных серверах и взаимодействующий через сетевые вызовы.</span><span class="sxs-lookup"><span data-stu-id="e6e03-112">In the previous figure, note how each client, microservice, and cloud-based [backing service](https://12factor.net/backing-services) executes as a separate process, running across different servers, all communicating via network-based calls.</span></span>

<span data-ttu-id="e6e03-113">Итак, что может быть не так?</span><span class="sxs-lookup"><span data-stu-id="e6e03-113">So, what could go wrong?</span></span>

- <span data-ttu-id="e6e03-114">Непредвиденная [задержка сети](https://www.techopedia.com/definition/8553/network-latency).</span><span class="sxs-lookup"><span data-stu-id="e6e03-114">Unexpected [network latency](https://www.techopedia.com/definition/8553/network-latency).</span></span>
- <span data-ttu-id="e6e03-115">Временные [сбои](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (временные ошибки подключения к сети).</span><span class="sxs-lookup"><span data-stu-id="e6e03-115">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (temporary network connectivity errors).</span></span>
- <span data-ttu-id="e6e03-116">Блокировка длительно выполняющейся синхронной операции.</span><span class="sxs-lookup"><span data-stu-id="e6e03-116">Blocking by a long-running synchronous operation.</span></span>
- <span data-ttu-id="e6e03-117">Ведущий процесс, который завершился сбоем, перезапускается или перемещается.</span><span class="sxs-lookup"><span data-stu-id="e6e03-117">A host process that has crashed and is being restarted or moved.</span></span>
- <span data-ttu-id="e6e03-118">Перегруженная микрослужба, которая не может ответить на короткое время.</span><span class="sxs-lookup"><span data-stu-id="e6e03-118">An overloaded microservice that can't respond for a short time.</span></span>
- <span data-ttu-id="e6e03-119">Операция onflight DevOps, такая как операция обновления или масштабирования.</span><span class="sxs-lookup"><span data-stu-id="e6e03-119">An in-flight DevOps operation such as an update or scaling operation.</span></span>
- <span data-ttu-id="e6e03-120">Операция Orchestrator, например перемещение службы с одного узла на другой.</span><span class="sxs-lookup"><span data-stu-id="e6e03-120">An Orchestrator operation such as moving a service from one node to another.</span></span>
- <span data-ttu-id="e6e03-121">Аппаратные сбои на оборудовании товара.</span><span class="sxs-lookup"><span data-stu-id="e6e03-121">Hardware failures from commodity hardware.</span></span>

<span data-ttu-id="e6e03-122">При развертывании распределенных служб в облачной инфраструктуре факторы из предыдущего списка становятся очень реальными, и вам необходимо создать архитектуру и разработать защищенные решения.</span><span class="sxs-lookup"><span data-stu-id="e6e03-122">When deploying distributed services into cloud-based infrastructure, the factors from the previous list become very real and you must architect and develop defensively to deal with them.</span></span>

<span data-ttu-id="e6e03-123">В небольших распределенных системах сбой будет менее частым, но по мере увеличения и уменьшения размера системы можно столкнуться с большим количеством таких проблем, когда частичный сбой становится нормальным.</span><span class="sxs-lookup"><span data-stu-id="e6e03-123">In a small-scale distributed system, failure will be less frequent, but as a system scales up and out, you can expect to experience more of these issues to a point where partial failure becomes normal operation.</span></span>

<span data-ttu-id="e6e03-124">Поэтому ваше приложение и инфраструктура должны быть устойчивыми.</span><span class="sxs-lookup"><span data-stu-id="e6e03-124">Therefore, your application and infrastructure must be resilient.</span></span> <span data-ttu-id="e6e03-125">В следующих разделах мы расскажем о защитных методах, которые можно добавить в приложение, и встроенных облачных функциях, которые можно использовать для подтверждения работы пользователя в виде маркеров.</span><span class="sxs-lookup"><span data-stu-id="e6e03-125">In the following sections, we'll explore defensive techniques that you can add to your application and built-in cloud features that you can leverage to help bullet-proof your user's experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e6e03-126">[Назад](azure-data-storage.md)
>[Вперед](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="e6e03-126">[Previous](azure-data-storage.md)
[Next](application-resiliency-patterns.md)</span></span>
