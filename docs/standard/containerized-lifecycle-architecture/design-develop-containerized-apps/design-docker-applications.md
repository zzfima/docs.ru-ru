---
title: Проектирование приложений Docker
description: Здесь поиска ссылки на подробное руководство по архитектуре микрослужб, потому что это раздел, он не подробно описана в данном руководстве.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: f31421cab7d2072441999231adfbe771a3f9a0f5
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220209"
---
# <a name="design-docker-applications"></a><span data-ttu-id="0c060-103">Проектирование приложений Docker</span><span class="sxs-lookup"><span data-stu-id="0c060-103">Design Docker applications</span></span>

<span data-ttu-id="0c060-104">Глава 1 представлены основные понятия о контейнерах и Docker.</span><span class="sxs-lookup"><span data-stu-id="0c060-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="0c060-105">Сведения о имеют базовый уровень сведения, необходимые для начала работы.</span><span class="sxs-lookup"><span data-stu-id="0c060-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="0c060-106">Но корпоративных приложений могут быть сложными и состоят из нескольких служб, вместо одной службы или контейнера.</span><span class="sxs-lookup"><span data-stu-id="0c060-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="0c060-107">В таких случаях не обязательно используйте необходимо знать дополнительных подходах к разработки, например сервисноориентированной архитектуры (SOA) и более сложных понятиях микрослужб и контейнер принципах оркестрации.</span><span class="sxs-lookup"><span data-stu-id="0c060-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="0c060-108">Рамки данного документа не ограничивается микрослужб, но для любого жизненный цикл приложения Docker таким образом, он не изучите архитектура микрослужб подробно потому, что также можно использовать контейнеры и Docker с помощью регулярного САН, фоновых задач или заданий, или даже с помощью методов развертывания монолитного приложения.</span><span class="sxs-lookup"><span data-stu-id="0c060-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="0c060-109">Тем не менее прежде чем углубиться в жизненном цикле приложения и DevOps, важно знать, как вы собираетесь проектирования и создания приложения и какие имеются варианты проектирования.</span><span class="sxs-lookup"><span data-stu-id="0c060-109">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0c060-110">[Назад](index.md)
>[Вперед](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="0c060-110">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>