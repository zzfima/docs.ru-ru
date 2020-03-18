---
title: Запуск, мониторинг рабочих сред Docker и управление ими
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
ms.date: 02/15/2019
ms.openlocfilehash: 900c361d5604f7fdaf41613287aa48c5381a9af7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "70295033"
---
# <a name="run-manage-and-monitor-docker-production-environments"></a><span data-ttu-id="8e526-103">Запуск, мониторинг рабочих сред Docker и управление ими</span><span class="sxs-lookup"><span data-stu-id="8e526-103">Run, manage, and monitor Docker production environments</span></span>

<span data-ttu-id="8e526-104">Концепция. Корпоративные приложения должны выполняться на высоком уровне доступности и масштабируемости, ИТ-операции должны контролировать и отслеживать среды и сами приложения.</span><span class="sxs-lookup"><span data-stu-id="8e526-104">Vision: Enterprise applications need to run with high availability and high scalability; IT operations need to be able to manage and monitor the environments and the applications themselves.</span></span>

<span data-ttu-id="8e526-105">Этот последний принцип жизненного цикла контейнерных приложений Docker касается методов выполнения и мониторинга приложений, а также управления ими в масштабируемых и высокодоступных производственных средах.</span><span class="sxs-lookup"><span data-stu-id="8e526-105">This last pillar in the containerized Docker applications life cycle is centered on how you can run, manage, and monitor your applications in scalable, high availability (HA) production environments.</span></span>

<span data-ttu-id="8e526-106">Запуск и выполнение контейнерных приложений в рабочей среде (в архитектуре инфраструктуры и с технологиями платформы) в значительной степени связаны и основаны на выбранной архитектуре и платформах разработки, которые рассматривались в первой главе этой электронной книги.</span><span class="sxs-lookup"><span data-stu-id="8e526-106">The way you run your containerized applications in production (infrastructure architecture and platform technologies) is very much related and based on the chosen architecture and development platforms discussed in Chapter 1 of this e-book.</span></span>

<span data-ttu-id="8e526-107">В этой главе содержатся сведения о конкретных продуктах и технологиях корпорации Майкрософт и других поставщиков, которые можно использовать для эффективного выполнения масштабируемых и распределенных приложений с высоким уровнем доступности, а также о том, как управлять ими и отслеживать их с точки зрения ИТ.</span><span class="sxs-lookup"><span data-stu-id="8e526-107">This chapter examines specific products and technologies from Microsoft and other vendors that you can use to effectively run scalable, HA distributed applications plus how you can manage and monitor them from the IT perspective.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8e526-108">[Назад](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
>[Вперед](run-microservices-based-applications-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="8e526-108">[Previous](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
[Next](run-microservices-based-applications-in-production.md)</span></span>
