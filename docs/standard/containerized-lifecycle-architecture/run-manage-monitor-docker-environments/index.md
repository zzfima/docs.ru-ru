---
title: Запуск, мониторинг рабочих сред Docker и управление ими
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 7c470a2d24b8807bdda10e1816bc5a430a5c63f1
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56834944"
---
# <a name="run-manage-and-monitor-docker-production-environments"></a><span data-ttu-id="c8eb9-103">Запуск, мониторинг рабочих сред Docker и управление ими</span><span class="sxs-lookup"><span data-stu-id="c8eb9-103">Run, manage, and monitor Docker production environments</span></span>

<span data-ttu-id="c8eb9-104">Концепция. Корпоративные приложения должны выполняться на высокий уровень доступности и масштабируемости; ИТ-операции должны иметь возможность управлять и отслеживать среды и сами приложения.</span><span class="sxs-lookup"><span data-stu-id="c8eb9-104">Vision: Enterprise applications need to run with high availability and high scalability; IT operations need to be able to manage and monitor the environments and the applications themselves.</span></span>

<span data-ttu-id="c8eb9-105">Этот последний принцип жизненного цикла контейнерных приложений Docker касается методов выполнения и мониторинга приложений, а также управления ими в масштабируемых и высокодоступных производственных средах.</span><span class="sxs-lookup"><span data-stu-id="c8eb9-105">This last pillar in the containerized Docker applications life cycle is centered on how you can run, manage, and monitor your applications in scalable, high availability (HA) production environments.</span></span>

<span data-ttu-id="c8eb9-106">Как контейнерные приложения выполняются в рабочей среде (инфраструктуры архитектуры и с технологиями платформы) является сильно связанные и на основе выбранных платформ архитектуры и разработки, обсуждается в главе 1 эту электронную книгу.</span><span class="sxs-lookup"><span data-stu-id="c8eb9-106">The way you run your containerized applications in production (infrastructure architecture and platform technologies) is very much related and based on the chosen architecture and development platforms discussed in Chapter 1 of this e-book.</span></span>

<span data-ttu-id="c8eb9-107">В этой главе рассматриваются конкретные продукты и технологии корпорации Microsoft и других производителей, которые можно использовать для эффективного выполнения масштабируемости, высокой ДОСТУПНОСТИ распределенных приложений, а также как управлять и отслеживать их с точки зрения ИТ.</span><span class="sxs-lookup"><span data-stu-id="c8eb9-107">This chapter examines specific products and technologies from Microsoft and other vendors that you can use to effectively run scalable, HA distributed applications plus how you can manage and monitor them from the IT perspective.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c8eb9-108">[Назад](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
>[Вперед](run-microservices-based-applications-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="c8eb9-108">[Previous](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
[Next](run-microservices-based-applications-in-production.md)</span></span>
