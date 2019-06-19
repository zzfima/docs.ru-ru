---
title: Проектирование приложений Docker
description: Здесь приведена ссылка на подробное руководство по архитектуре микрослужб, так как эта тема не описана в данном руководстве подробно.
ms.date: 02/15/2019
ms.openlocfilehash: 535b6cefb7371014527032972ec27ebfe4b67ebc
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644671"
---
# <a name="design-docker-applications"></a><span data-ttu-id="96ee1-103">Проектирование приложений Docker</span><span class="sxs-lookup"><span data-stu-id="96ee1-103">Design Docker applications</span></span>

<span data-ttu-id="96ee1-104">В главе 1 представлены основные понятия о контейнерах и Docker.</span><span class="sxs-lookup"><span data-stu-id="96ee1-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="96ee1-105">Это минимальный объем информации, необходимый для начала работы.</span><span class="sxs-lookup"><span data-stu-id="96ee1-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="96ee1-106">Однако корпоративные приложения могут быть сложными и состоять из нескольких служб, а не одной службы или одного контейнера.</span><span class="sxs-lookup"><span data-stu-id="96ee1-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="96ee1-107">При таких вариантах использования нужно знать о других подходах к разработке, например сервисноориентированной архитектуре (SOA), а также более сложных понятиях, связанных с микрослужбами и оркестрацией контейнеров.</span><span class="sxs-lookup"><span data-stu-id="96ee1-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="96ee1-108">Этот документ посвящен не микрослужбам, а жизненному циклу любого приложения Docker, поэтому архитектура микрослужб не рассматривается в нем подробно, так как контейнеры и Docker также можно использовать с обычной SOA, фоновыми задачами или заданиями и даже при развертывании монолитных приложений.</span><span class="sxs-lookup"><span data-stu-id="96ee1-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="96ee1-109">**Дополнительные сведения**. Подробнее о корпоративных приложениях и архитектуре микрослужб см. в руководстве [Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET](../../microservices-architecture/index.md), которое можно скачать на странице <https://aka.ms/MicroservicesEbook>.</span><span class="sxs-lookup"><span data-stu-id="96ee1-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices-architecture/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="96ee1-110">Но, прежде чем углубиться в жизненный цикл приложения и DevOps, важно понимать, как вы собираетесь проектировать и создавать приложение и какие варианты проектирования доступны.</span><span class="sxs-lookup"><span data-stu-id="96ee1-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="96ee1-111">[Назад](index.md)
>[Вперед](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="96ee1-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
