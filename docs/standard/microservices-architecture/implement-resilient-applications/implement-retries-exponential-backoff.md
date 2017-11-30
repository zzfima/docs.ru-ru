---
title: "Реализация повторных попыток с экспоненциально растущим"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализация повторных попыток с экспоненциально растущим"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8ad8c6363ddff59915efc076161fe6b76074bbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="72398-104">Реализация повторных попыток с экспоненциально растущим</span><span class="sxs-lookup"><span data-stu-id="72398-104">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="72398-105">[*Число повторов с экспоненциально растущим* ](https://docs.microsoft.com/azure/architecture/patterns/retry) — это метод, который пытается повторить операцию с экспоненциально увеличивающейся временем ожидания, пока не будет достигнуто максимальное число повторных попыток ( [экспоненциально растущим](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="72398-105">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="72398-106">Этот метод выполняет тот факт, что облачные ресурсы периодически недоступен на несколько секунд, по любой причине.</span><span class="sxs-lookup"><span data-stu-id="72398-106">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="72398-107">Например модуль может быть при перемещении контейнер на другой узел в кластере балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="72398-107">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="72398-108">В это время некоторых запросов может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="72398-108">During that time, some requests might fail.</span></span> <span data-ttu-id="72398-109">Другим примером может быть базы данных, таких как SQL Azure, где базы данных можно переместить на другой сервер для балансировки нагрузки с базы данных становится недоступным в течение нескольких секунд.</span><span class="sxs-lookup"><span data-stu-id="72398-109">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="72398-110">Существует множество подходов, чтобы реализовать логику повторных попыток с экспоненциально растущим.</span><span class="sxs-lookup"><span data-stu-id="72398-110">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="72398-111">[Предыдущие] (partial сбой strategies.md) [Далее] (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="72398-111">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
