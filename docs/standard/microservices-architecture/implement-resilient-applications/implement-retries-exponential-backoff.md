---
title: Реализация повторных попыток с экспоненциальной выдержкой
description: Узнайте, как реализовать метод повторных попыток с экспоненциальной задержкой.
ms.date: 10/16/2018
ms.openlocfilehash: 1b948e399495eeb12016006442ac08d2b04f2e69
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644215"
---
# <a name="implement-retries-with-exponential-backoff"></a><span data-ttu-id="e3ca2-103">Реализация повторных попыток с экспоненциальной выдержкой</span><span class="sxs-lookup"><span data-stu-id="e3ca2-103">Implement retries with exponential backoff</span></span>

<span data-ttu-id="e3ca2-104">[*Повторные попытки с экспоненциальной задержкой*](/azure/architecture/patterns/retry) — это метод, который пытается повторить операцию с экспоненциально растущим временем ожидания, пока не будет достигнуто максимальное число повторных попыток ([экспоненциальная задержка](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="e3ca2-104">[*Retries with exponential backoff*](/azure/architecture/patterns/retry) is a technique that retries an operation, with an exponentially increasing wait time, up to a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="e3ca2-105">Этот метод учитывает тот факт, что облачные ресурсы могут быть периодически недоступны в течение нескольких секунд по различным причинам.</span><span class="sxs-lookup"><span data-stu-id="e3ca2-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="e3ca2-106">Например, оркестратор может перемещать контейнер на другой узел в кластере для балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="e3ca2-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="e3ca2-107">В течение этого времени некоторые запросы могут завершиться с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e3ca2-107">During that time, some requests might fail.</span></span> <span data-ttu-id="e3ca2-108">Другой пример — база данных, например база данных SQL Azure. В этом случае база данных может перемещаться на другой сервер для балансировки нагрузки. Во время этого перемещения она может быть недоступна в течение нескольких секунд.</span><span class="sxs-lookup"><span data-stu-id="e3ca2-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="e3ca2-109">Существует множество подходов для реализации логики повторных попыток с экспоненциальной выдержкой.</span><span class="sxs-lookup"><span data-stu-id="e3ca2-109">There are many approaches to implement retries logic with exponential backoff.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e3ca2-110">[Назад](partial-failure-strategies.md)
>[Вперед](implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="e3ca2-110">[Previous](partial-failure-strategies.md)
[Next](implement-resilient-entity-framework-core-sql-connections.md)</span></span>
