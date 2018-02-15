---
title: "Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2f7ed0c9ebf1c80ae6cae4311b2682d3cc161623
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)

Служба Azure контейнера оптимизирует конфигурации популярных средств с открытым исходным кодом и технологии специально для Azure. Вы получаете открытое решение, который обеспечивает совместимость для вашего контейнеров и конфигурации приложения. Выбрать размер, количество узлов и средств orchestrator. Служба Azure контейнера обрабатывает инфраструктуры.

Если вы уже работаете с открытым исходным кодом orchestrators как Kubernetes помощью Docker Swarm и контроллера домена/OS, не нужно изменять существующие методик управления для перемещения рабочих нагрузок контейнера в облако. Используйте средства управления приложения, вы уже знакомы с и подключения через стандартные конечные точки API для orchestrator по своему усмотрению.

Эти orchestrators — зрелой среды при использовании контейнеров Linux Docker, но они также поддержка контейнеров Windows как части 2017 г. (некоторые более ранней версии, некоторые в последнее время в зависимости от orchestrator).

Например, в Kubernetes, поддержка контейнеров является машинный код (высокоприоритетным) с помощью контейнеров Windows на Kubernetes также очень эффективный и надежный (в режиме предварительного просмотра, пока не раньше попадают 2017 г.).

>[!div class="step-by-step"]
[Назад](when-to-deploy-windows-containers-to-service-fabric.md)
[Вперед](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
