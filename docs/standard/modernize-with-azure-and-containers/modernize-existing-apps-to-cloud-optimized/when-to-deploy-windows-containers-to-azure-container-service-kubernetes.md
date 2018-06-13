---
title: Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)
description: Модернизировать существующие приложения .NET с контейнерами Windows и облако Azure | Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b7f106e2b79a2c6bb24733debf7f4828505d66a6
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958174"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Если развернуть контейнеры Windows Azure контейнер службе (то есть, Kubernetes)

Служба Azure контейнера оптимизирует конфигурации популярных средств с открытым исходным кодом и технологии специально для Azure. Вы получаете открытое решение, который обеспечивает совместимость для вашего контейнеров и конфигурации приложения. Выбрать размер, количество узлов и средств orchestrator. Служба Azure контейнера обрабатывает инфраструктуры.

Если вы уже работаете с открытым исходным кодом orchestrators как Kubernetes помощью Docker Swarm и контроллера домена/OS, не нужно изменять существующие методик управления для перемещения рабочих нагрузок контейнера в облако. Используйте средства управления приложения, которые вы уже знакомы с и подключения через стандартные конечные точки API для orchestrator по своему усмотрению.

Эти orchestrators — зрелой среды, если вы используете контейнеры Linux Docker, но может быть только в состоянии предварительной версии для контейнеров Windows.

Например, в Kubernetes, поддержку контейнеры с помощью контейнеров Windows на Kubernetes машинный код (высокоприоритетным) может использоваться (в предварительной версии в ACS, начиная с ранним 2018).

Важное замечание: доработанной и «дополнительные PaaS» версия ACS (контейнера службы Azure) для Kubernetes — AKS (Kubernetes службы Azure), однако контейнеры Windows по-прежнему не поддерживаются начиная с Q2 2018, но скоро будет поддерживаться.

>[!div class="step-by-step"]
[Назад](when-to-deploy-windows-containers-to-service-fabric.md)
[Вперед](choosing-azure-compute-options-for-container-based-applications.md)
