---
title: "Реализация устойчивых приложений"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация устойчивых приложений"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a6fc2f4c963d857be06e194468e2f8514437dd1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="ba81a-104">Реализация устойчивых приложений</span><span class="sxs-lookup"><span data-stu-id="ba81a-104">Implementing Resilient Applications</span></span>

<span data-ttu-id="ba81a-105">*В приложениях на основе микрослужб и облачных приложениях должна быть предусмотрена обработка частичных сбоев, которые так или иначе будут происходить. Приложение следует проектировать так, чтобы оно было устойчиво к этим сбоям.*</span><span class="sxs-lookup"><span data-stu-id="ba81a-105">*Your microservice and cloud based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="ba81a-106">Устойчивость — это возможность восстановления после сбоев и продолжение работы.</span><span class="sxs-lookup"><span data-stu-id="ba81a-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="ba81a-107">Исходить следует из того, что избежать сбоев невозможно и на них нужно реагировать таким образом, чтобы избежать простоев или потери данных.</span><span class="sxs-lookup"><span data-stu-id="ba81a-107">It is not about avoiding failures, but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="ba81a-108">Цель устойчивости — вернуть приложение в полностью функционирующее состояние после сбоя.</span><span class="sxs-lookup"><span data-stu-id="ba81a-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="ba81a-109">Разработать и развернуть приложение на основе микрослужб уже достаточно сложно.</span><span class="sxs-lookup"><span data-stu-id="ba81a-109">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="ba81a-110">Но помимо этого, оно должно работать в среде, в которой неизбежны определенные неполадки.</span><span class="sxs-lookup"><span data-stu-id="ba81a-110">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="ba81a-111">Поэтому приложение должно быть устойчивым.</span><span class="sxs-lookup"><span data-stu-id="ba81a-111">Therefore, your application should be resilient.</span></span> <span data-ttu-id="ba81a-112">Оно должно уметь справляться с частичными сбоями, такими как отключения сети либо аварийные сбои узлов или виртуальных машин в облаке.</span><span class="sxs-lookup"><span data-stu-id="ba81a-112">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="ba81a-113">Даже перенос микрослужб (контейнеров) в другой узел кластера может приводить к кратковременным сбоям в приложении.</span><span class="sxs-lookup"><span data-stu-id="ba81a-113">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="ba81a-114">Многие отдельные компоненты приложения также должны включать функции мониторинга работоспособности.</span><span class="sxs-lookup"><span data-stu-id="ba81a-114">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="ba81a-115">Следуя рекомендациям этой главы, можно создать приложение, которое будет продолжать работать, несмотря на временные простои или небольшие неисправности, возникающие в сложных и облачных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="ba81a-115">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ba81a-116">[Назад] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Далее] (handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="ba81a-116">[Previous] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Next] (handle-partial-failure.md)</span></span>
