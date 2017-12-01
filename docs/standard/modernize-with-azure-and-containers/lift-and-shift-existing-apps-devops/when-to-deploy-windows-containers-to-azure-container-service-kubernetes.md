---
title: "Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: f5ba7aa2cf14e7ca9f3a1f3eb12bbe236dca7e97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)

Служба Azure контейнера оптимизирует конфигурации популярных средств с открытым исходным кодом и технологии специально для Azure. Вы получаете открытое решение, который обеспечивает совместимость для вашего контейнеров и конфигурации приложения. Выбрать размер, количество узлов и средств orchestrator. Служба Azure контейнера обрабатывает инфраструктуры.

Если вы уже работаете с открытым исходным кодом orchestrators как Kubernetes помощью Docker Swarm и контроллера домена/OS, не нужно изменять существующие методик управления для перемещения рабочих нагрузок контейнера в облако. Используйте средства управления приложения, вы уже знакомы с и подключения через стандартные конечные точки API для orchestrator по своему усмотрению.

Эти orchestrators — зрелой среды при использовании контейнеров Linux Docker, но они также поддержка контейнеров Windows как части 2017 г. (некоторые более ранней версии, некоторые в последнее время в зависимости от orchestrator).

Например, в Kubernetes, поддержка контейнеров является машинный код (высокоприоритетным) с помощью контейнеров Windows на Kubernetes также очень эффективный и надежный (в режиме предварительного просмотра, пока не раньше попадают 2017 г.).

>[!div class="step-by-step"]
[Назад](when-to-deploy-windows-containers-to-service-fabric.md)
[Вперед](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
