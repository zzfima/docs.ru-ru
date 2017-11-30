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
# <a name="implementing-retries-with-exponential-backoff"></a>Реализация повторных попыток с экспоненциально растущим

[*Число повторов с экспоненциально растущим* ](https://docs.microsoft.com/azure/architecture/patterns/retry) — это метод, который пытается повторить операцию с экспоненциально увеличивающейся временем ожидания, пока не будет достигнуто максимальное число повторных попыток ( [экспоненциально растущим](https://en.wikipedia.org/wiki/Exponential_backoff)). Этот метод выполняет тот факт, что облачные ресурсы периодически недоступен на несколько секунд, по любой причине. Например модуль может быть при перемещении контейнер на другой узел в кластере балансировки нагрузки. В это время некоторых запросов может завершиться ошибкой. Другим примером может быть базы данных, таких как SQL Azure, где базы данных можно переместить на другой сервер для балансировки нагрузки с базы данных становится недоступным в течение нескольких секунд.

Существует множество подходов, чтобы реализовать логику повторных попыток с экспоненциально растущим.


>[!div class="step-by-step"]
[Предыдущие] (partial сбой strategies.md) [Далее] (implement-resilient-entity-framework-core-sql-connections.md)
