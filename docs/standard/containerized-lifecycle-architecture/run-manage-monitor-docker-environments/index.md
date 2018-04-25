---
title: Запуск, мониторинг рабочих сред Docker и управление ими
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 41c170b5e58d92c6e669de48c1f41caf5b2aa6e8
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="run-manage-and-monitor-docker-production-environments"></a><span data-ttu-id="948b6-103">Запуск, мониторинг рабочих сред Docker и управление ими</span><span class="sxs-lookup"><span data-stu-id="948b6-103">Run, manage, and monitor Docker production environments</span></span>

<span data-ttu-id="948b6-104">Концепция. Корпоративные приложения должны выполняться на высоком уровне доступности и масштабируемости, ИТ-операции должны контролировать и отслеживать среды и сами приложения.</span><span class="sxs-lookup"><span data-stu-id="948b6-104">Vision: Enterprise applications need to run with high availability and high scalability; IT operations need to be able to manage and monitor the environments and the applications themselves.</span></span>

<span data-ttu-id="948b6-105">Этот последний принцип жизненного цикла контейнерных приложений Docker касается методов выполнения и мониторинга приложений, а также управления ими в масштабируемых и высокодоступных производственных средах.</span><span class="sxs-lookup"><span data-stu-id="948b6-105">This last pillar in the containerized Docker applications life cycle is centered on how you can run, manage, and monitor your applications in scalable, high availability (HA) production environments.</span></span>

<span data-ttu-id="948b6-106">Запуск и выполнение контейнерных приложений в рабочей среде (в архитектуре инфраструктуры и с технологиями платформы) в значительной степени связаны и полностью основаны на выбранной архитектуре и платформах разработки, которые рассматривались в первой главе этой электронной книги.</span><span class="sxs-lookup"><span data-stu-id="948b6-106">How you run your containerized applications in production (infrastructure architecture and platform technologies) is also very much related and completely founded on the chosen architecture and development platforms that we looked at in the Chapter 1 of this e-book.</span></span> <span data-ttu-id="948b6-107">В этой главе содержатся сведения о конкретных продуктах и технологиях корпорации Майкрософт и других поставщиков, которые можно использовать для эффективного выполнения высокомасштабируемых и распределенных приложений с высоким уровнем доступности, а также о том, как управлять ими и отслеживать их с точки зрения ИТ.</span><span class="sxs-lookup"><span data-stu-id="948b6-107">This chapter examines specific products and technologies from Microsoft and other vendors that you can use to effectively run highly scalable, HA distributed applications plus how you can manage and monitor them from the IT perspective.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="948b6-108">[Назад] (../docker-devops-workflow/docker-application-outer-loop-devops-workflow.md) [Далее] (run-microservices-based-applications-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="948b6-108">[Previous] (../docker-devops-workflow/docker-application-outer-loop-devops-workflow.md) [Next] (run-microservices-based-applications-in-production.md)</span></span>
