---
title: Модели связи, ориентированные на облако
description: Сведения о вопросах взаимодействия с основными службами в собственных облачных приложениях
author: robvet
ms.date: 08/31/2019
ms.openlocfilehash: 3bda9baa516b7bd8f893e0f58bbe5e2bfde2b61d
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841147"
---
# <a name="cloud-native-communication-patterns"></a><span data-ttu-id="8729f-103">Модели связи, ориентированные на облако</span><span class="sxs-lookup"><span data-stu-id="8729f-103">Cloud-native communication patterns</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="8729f-104">При создании собственной облачной системы обмен данными является значительным решением по проектированию.</span><span class="sxs-lookup"><span data-stu-id="8729f-104">When constructing a cloud-native system, communication becomes a significant design decision.</span></span> <span data-ttu-id="8729f-105">Как клиентское приложение клиентского взаимодействия взаимодействует с серверной микрослужбой?</span><span class="sxs-lookup"><span data-stu-id="8729f-105">How does a front-end client application communicate with a back-end microservice?</span></span> <span data-ttu-id="8729f-106">Как серверные микрослужбы взаимодействуют друг с другом?</span><span class="sxs-lookup"><span data-stu-id="8729f-106">How do back-end microservices communicate with each other?</span></span> <span data-ttu-id="8729f-107">Каковы принципы, шаблоны и рекомендации, которые следует учитывать при реализации взаимодействия в собственных приложениях в облаке?</span><span class="sxs-lookup"><span data-stu-id="8729f-107">What are the principles, patterns, and best practices to consider when implementing communication in cloud-native applications?</span></span>

## <a name="communication-considerations"></a><span data-ttu-id="8729f-108">Вопросы связи</span><span class="sxs-lookup"><span data-stu-id="8729f-108">Communication considerations</span></span>

<span data-ttu-id="8729f-109">В монолитном приложении обмен данными осуществляется очень просто.</span><span class="sxs-lookup"><span data-stu-id="8729f-109">In a monolithic application, communication is straightforward.</span></span> <span data-ttu-id="8729f-110">Модули кода выполняются вместе в одном исполняемом пространстве (процессе) на сервере.</span><span class="sxs-lookup"><span data-stu-id="8729f-110">The code modules execute together in the same executable space (process) on a server.</span></span> <span data-ttu-id="8729f-111">Такой подход может иметь преимущества производительности, так как все они работают вместе в общей памяти, но в результате образуется тесно связанный код, который усложняет обслуживание, развитие и масштабирование.</span><span class="sxs-lookup"><span data-stu-id="8729f-111">This approach can have performance advantages as everything runs together in shared memory, but results in tightly coupled code that becomes difficult to maintain, evolve, and scale.</span></span>

<span data-ttu-id="8729f-112">Облачные системы реализуют архитектуру на основе микрослужб с множеством небольших независимых микрослужб.</span><span class="sxs-lookup"><span data-stu-id="8729f-112">Cloud-native systems implement a microservice-based architecture with many small, independent microservices.</span></span> <span data-ttu-id="8729f-113">Каждая микрослужба выполняется в отдельном процессе и обычно выполняется внутри контейнера, развернутого в *кластере*.</span><span class="sxs-lookup"><span data-stu-id="8729f-113">Each microservice executes in a separate process and typically runs inside a container that is deployed to a *cluster*.</span></span>

<span data-ttu-id="8729f-114">Кластер группирует пулы виртуальных машин вместе, образуя высокодоступную среду.</span><span class="sxs-lookup"><span data-stu-id="8729f-114">A cluster groups a pool of virtual machines together to form a highly available environment.</span></span> <span data-ttu-id="8729f-115">Управление ими осуществляется с помощью средства оркестрации, которое отвечает за развертывание и Управление контейнерными микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="8729f-115">They're managed with an orchestration tool, which is responsible for deploying and managing the containerized microservices.</span></span> <span data-ttu-id="8729f-116">На рис. 4-1 показан кластер [Kubernetes](https://kubernetes.io) , развернутый в облаке Azure с полностью управляемыми [службами Kubernetes Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).</span><span class="sxs-lookup"><span data-stu-id="8729f-116">Figure 4-1 shows a [Kubernetes](https://kubernetes.io) cluster deployed into the Azure cloud with the fully managed [Azure Kubernetes Services](https://docs.microsoft.com/azure/aks/intro-kubernetes).</span></span>

![Кластер Kubernetes в Azure](./media/kubernetes-cluster-in-azure.png)

<span data-ttu-id="8729f-118">**Рис. 4-1**.</span><span class="sxs-lookup"><span data-stu-id="8729f-118">**Figure 4-1**.</span></span> <span data-ttu-id="8729f-119">Кластер Kubernetes в Azure</span><span class="sxs-lookup"><span data-stu-id="8729f-119">A Kubernetes cluster in Azure</span></span>

<span data-ttu-id="8729f-120">В кластере микрослужбы взаимодействуют друг с другом через API-интерфейсы и технологии обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8729f-120">Across the cluster, microservices communicate with each other through APIs and messaging technologies.</span></span>

<span data-ttu-id="8729f-121">Так как они предоставляют множество преимуществ, микрослужбы не являются бесплатным обедом.</span><span class="sxs-lookup"><span data-stu-id="8729f-121">While they provide many benefits, microservices are no free lunch.</span></span> <span data-ttu-id="8729f-122">Локальные вызовы внутрипроцессного метода между компонентами теперь заменяются сетевыми вызовами.</span><span class="sxs-lookup"><span data-stu-id="8729f-122">Local in-process method calls between components are now replaced with network calls.</span></span> <span data-ttu-id="8729f-123">Каждая микрослужба должна взаимодействовать по сетевому протоколу, что повышает сложность системы:</span><span class="sxs-lookup"><span data-stu-id="8729f-123">Each microservice must communicate over a network protocol, which adds complexity to your system:</span></span>

- <span data-ttu-id="8729f-124">Перегрузка сети, задержка и временные сбои являются постоянной задачей.</span><span class="sxs-lookup"><span data-stu-id="8729f-124">Network congestion, latency, and transient faults are a constant concern.</span></span>

- <span data-ttu-id="8729f-125">Обеспечение устойчивости (то есть повтор невыполненных запросов) является обязательным.</span><span class="sxs-lookup"><span data-stu-id="8729f-125">Resiliency (that is, retrying failed requests) is essential.</span></span>

- <span data-ttu-id="8729f-126">Для сохранения стабильного состояния некоторые вызовы должны быть [идемпотентными](https://www.restapitutorial.com/lessons/idempotency.html) .</span><span class="sxs-lookup"><span data-stu-id="8729f-126">Some calls must be [idempotent](https://www.restapitutorial.com/lessons/idempotency.html) as to keep consistent state.</span></span>

- <span data-ttu-id="8729f-127">Каждая микрослужба должна проходить проверку подлинности и авторизовать вызовы.</span><span class="sxs-lookup"><span data-stu-id="8729f-127">Each microservice must authenticate and authorize calls.</span></span>

- <span data-ttu-id="8729f-128">Каждое сообщение должно быть сериализовано, а затем десериализовано, что может быть дорогостоящим.</span><span class="sxs-lookup"><span data-stu-id="8729f-128">Each message must be serialized and then deserialized - which can be expensive.</span></span>

- <span data-ttu-id="8729f-129">Шифрование и расшифровка сообщений становятся важными.</span><span class="sxs-lookup"><span data-stu-id="8729f-129">Message encryption/decryption becomes important.</span></span>

<span data-ttu-id="8729f-130">Микрослужбы [.NET книги — это архитектура для упакованных в контейнеры приложений .NET](https://docs.microsoft.com/dotnet/standard/microservices-architecture/), доступных бесплатно корпорации Майкрософт, которая предоставляет подробные сведения о шаблонах связи для приложений микрослужб.</span><span class="sxs-lookup"><span data-stu-id="8729f-130">The book [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/standard/microservices-architecture/), available for free from Microsoft, provides an in-depth coverage of communication patterns for microservice applications.</span></span> <span data-ttu-id="8729f-131">В этой главе представлен общий обзор этих шаблонов и параметры реализации, доступные в облаке Azure.</span><span class="sxs-lookup"><span data-stu-id="8729f-131">In this chapter, we provide a high-level overview of these patterns along with implementation options available in the Azure cloud.</span></span>

<span data-ttu-id="8729f-132">В этой главе мы сначала будем обращаться к взаимодействию между внешними приложениями и внутренними микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="8729f-132">In this chapter, we'll first address communication between front-end applications and back-end microservices.</span></span> <span data-ttu-id="8729f-133">Затем мы рассмотрим взаимосвязь между внутренними микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="8729f-133">We'll then look at back-end microservices communicate with each other.</span></span> <span data-ttu-id="8729f-134">Мы рассмотрим технологию связи up and gRPC.</span><span class="sxs-lookup"><span data-stu-id="8729f-134">We'll explore the up and gRPC communication technology.</span></span> <span data-ttu-id="8729f-135">Наконец, мы рассмотрим новые инновационные шаблоны связи с помощью технологии сетчатой службы.</span><span class="sxs-lookup"><span data-stu-id="8729f-135">Finally, we'll look new innovative communication patterns using service mesh technology.</span></span> <span data-ttu-id="8729f-136">Мы также посмотрим, как облако Azure предоставляет различные виды *резервных служб* для поддержки обмена данными в облаке.</span><span class="sxs-lookup"><span data-stu-id="8729f-136">We'll also see how the Azure cloud provides different kinds of *backing services* to support cloud-native communication.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8729f-137">[Назад](other-deployment-options.md)
>[Вперед](front-end-communication.md)</span><span class="sxs-lookup"><span data-stu-id="8729f-137">[Previous](other-deployment-options.md)
[Next](front-end-communication.md)</span></span>
