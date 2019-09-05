---
title: Реализация устойчивых приложений
description: Сведения об устойчивости — основном понятии в архитектуре микрослужб. Вам необходимо знать, как правильно обрабатывать возникающие временные сбои.
ms.date: 10/16/2018
ms.openlocfilehash: 766349e72389f848b0a741b020707cc7acf3410d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "70295129"
---
# <a name="implement-resilient-applications"></a><span data-ttu-id="cf036-104">Реализация устойчивых приложений</span><span class="sxs-lookup"><span data-stu-id="cf036-104">Implement Resilient Applications</span></span>

<span data-ttu-id="cf036-105">*В приложениях на основе микрослужб и облачных приложениях должна быть предусмотрена обработка частичных сбоев, которые так или иначе будут происходить. Приложение следует проектировать так, чтобы оно было устойчиво к этим сбоям.*</span><span class="sxs-lookup"><span data-stu-id="cf036-105">*Your microservice and cloud-based applications must embrace the partial failures that will certainly occur eventually. You must design your application to be resilient to those partial failures.*</span></span>

<span data-ttu-id="cf036-106">Устойчивость — это возможность восстановления после сбоев и продолжение работы.</span><span class="sxs-lookup"><span data-stu-id="cf036-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="cf036-107">Исходить следует из того, что избежать сбоев невозможно, и на них нужно реагировать так, чтобы избежать простоев или потери данных.</span><span class="sxs-lookup"><span data-stu-id="cf036-107">It isn't about avoiding failures but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="cf036-108">Цель устойчивости — вернуть приложение в полностью функционирующее состояние после сбоя.</span><span class="sxs-lookup"><span data-stu-id="cf036-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="cf036-109">Разработать и развернуть приложение на основе микрослужб достаточно сложно.</span><span class="sxs-lookup"><span data-stu-id="cf036-109">It's challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="cf036-110">Но помимо этого, оно должно работать в среде, в которой неизбежны определенные неполадки.</span><span class="sxs-lookup"><span data-stu-id="cf036-110">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="cf036-111">Поэтому приложение должно быть устойчивым.</span><span class="sxs-lookup"><span data-stu-id="cf036-111">Therefore, your application should be resilient.</span></span> <span data-ttu-id="cf036-112">Оно должно уметь справляться с частичными сбоями, такими как отключения сети либо аварийные сбои узлов или виртуальных машин в облаке.</span><span class="sxs-lookup"><span data-stu-id="cf036-112">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="cf036-113">Даже перенос микрослужб (контейнеров) в другой узел кластера может приводить к кратковременным сбоям в приложении.</span><span class="sxs-lookup"><span data-stu-id="cf036-113">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="cf036-114">Многие отдельные компоненты приложения также должны включать функции мониторинга работоспособности.</span><span class="sxs-lookup"><span data-stu-id="cf036-114">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="cf036-115">Следуя рекомендациям этой главы, можно создать приложение, которое будет продолжать работать, несмотря на временные простои или небольшие неисправности, возникающие в сложных и облачных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="cf036-115">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cf036-116">[Назад](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[Вперед](handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="cf036-116">[Previous](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Next](handle-partial-failure.md)</span></span>
