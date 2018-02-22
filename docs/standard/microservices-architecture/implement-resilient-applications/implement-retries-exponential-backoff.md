---
title: "Реализация повторных попыток с экспоненциальной выдержкой"
description: "Архитектура микрослужб .NET для контейнерных приложений .NET | Реализация повторных попыток с экспоненциальной выдержкой"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7ed97b750d6e3f2aa5def72e90e070a49a7c0e63
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="d4a36-104">Реализация повторных попыток с экспоненциальной выдержкой</span><span class="sxs-lookup"><span data-stu-id="d4a36-104">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="d4a36-105">[*Повторные попытки с экспоненциальной выдержкой*](https://docs.microsoft.com/azure/architecture/patterns/retry) — это метод, который пытается повторить операцию с экспоненциально растущим временем ожидания, пока не будет достигнуто максимальное число повторных попыток ([экспоненциальная выдержка](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="d4a36-105">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="d4a36-106">Этот метод учитывает тот факт, что облачные ресурсы могут быть периодически недоступны в течение нескольких секунд по различным причинам.</span><span class="sxs-lookup"><span data-stu-id="d4a36-106">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="d4a36-107">Например, оркестратор может перемещать контейнер на другой узел в кластере для балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="d4a36-107">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="d4a36-108">В течение этого времени некоторые запросы могут завершиться с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d4a36-108">During that time, some requests might fail.</span></span> <span data-ttu-id="d4a36-109">Другой пример — база данных, например база данных SQL Azure. В этом случае база данных может перемещаться на другой сервер для балансировки нагрузки. Во время этого перемещения она может быть недоступна в течение нескольких секунд.</span><span class="sxs-lookup"><span data-stu-id="d4a36-109">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="d4a36-110">Существует множество подходов для реализации логики повторных попыток с экспоненциальной выдержкой.</span><span class="sxs-lookup"><span data-stu-id="d4a36-110">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="d4a36-111">[Назад] (partial-failure-strategies.md) [Далее] (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="d4a36-111">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
