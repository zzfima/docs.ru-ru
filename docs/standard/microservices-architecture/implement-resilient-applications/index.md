---
title: Реализация устойчивых приложений
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация устойчивых приложений
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 211814eff0f2aaf0cf71a19cfcaaeb44924fb6f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="566d4-103">Реализация устойчивых приложений</span><span class="sxs-lookup"><span data-stu-id="566d4-103">Implementing Resilient Applications</span></span>

<span data-ttu-id="566d4-104">*В приложениях на основе микрослужб и облачных приложениях должна быть предусмотрена обработка частичных сбоев, которые так или иначе будут происходить. Приложение следует проектировать так, чтобы оно было устойчиво к этим сбоям.*</span><span class="sxs-lookup"><span data-stu-id="566d4-104">*Your microservice and cloud based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="566d4-105">Устойчивость — это возможность восстановления после сбоев и продолжение работы.</span><span class="sxs-lookup"><span data-stu-id="566d4-105">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="566d4-106">Исходить следует из того, что избежать сбоев невозможно и на них нужно реагировать таким образом, чтобы избежать простоев или потери данных.</span><span class="sxs-lookup"><span data-stu-id="566d4-106">It is not about avoiding failures, but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="566d4-107">Цель устойчивости — вернуть приложение в полностью функционирующее состояние после сбоя.</span><span class="sxs-lookup"><span data-stu-id="566d4-107">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="566d4-108">Разработать и развернуть приложение на основе микрослужб уже достаточно сложно.</span><span class="sxs-lookup"><span data-stu-id="566d4-108">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="566d4-109">Но помимо этого, оно должно работать в среде, в которой неизбежны определенные неполадки.</span><span class="sxs-lookup"><span data-stu-id="566d4-109">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="566d4-110">Поэтому приложение должно быть устойчивым.</span><span class="sxs-lookup"><span data-stu-id="566d4-110">Therefore, your application should be resilient.</span></span> <span data-ttu-id="566d4-111">Оно должно уметь справляться с частичными сбоями, такими как отключения сети либо аварийные сбои узлов или виртуальных машин в облаке.</span><span class="sxs-lookup"><span data-stu-id="566d4-111">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="566d4-112">Даже перенос микрослужб (контейнеров) в другой узел кластера может приводить к кратковременным сбоям в приложении.</span><span class="sxs-lookup"><span data-stu-id="566d4-112">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="566d4-113">Многие отдельные компоненты приложения также должны включать функции мониторинга работоспособности.</span><span class="sxs-lookup"><span data-stu-id="566d4-113">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="566d4-114">Следуя рекомендациям этой главы, можно создать приложение, которое будет продолжать работать, несмотря на временные простои или небольшие неисправности, возникающие в сложных и облачных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="566d4-114">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="566d4-115">[Назад] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Далее] (handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="566d4-115">[Previous] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Next] (handle-partial-failure.md)</span></span>
