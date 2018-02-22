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
# <a name="implementing-retries-with-exponential-backoff"></a>Реализация повторных попыток с экспоненциальной выдержкой

[*Повторные попытки с экспоненциальной выдержкой*](https://docs.microsoft.com/azure/architecture/patterns/retry) — это метод, который пытается повторить операцию с экспоненциально растущим временем ожидания, пока не будет достигнуто максимальное число повторных попыток ([экспоненциальная выдержка](https://en.wikipedia.org/wiki/Exponential_backoff)). Этот метод учитывает тот факт, что облачные ресурсы могут быть периодически недоступны в течение нескольких секунд по различным причинам. Например, оркестратор может перемещать контейнер на другой узел в кластере для балансировки нагрузки. В течение этого времени некоторые запросы могут завершиться с ошибкой. Другой пример — база данных, например база данных SQL Azure. В этом случае база данных может перемещаться на другой сервер для балансировки нагрузки. Во время этого перемещения она может быть недоступна в течение нескольких секунд.

Существует множество подходов для реализации логики повторных попыток с экспоненциальной выдержкой.


>[!div class="step-by-step"]
[Назад] (partial-failure-strategies.md) [Далее] (implement-resilient-entity-framework-core-sql-connections.md)
