---
title: Когда следует развертывать контейнеры Windows в службе контейнеров Azure (т. е. Kubernetes)
description: Модернизировать существующих приложений .NET с помощью Azure Cloud and Windows Containers | Когда следует развертывать контейнеры Windows в службе контейнеров Azure (т. е. Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577947"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Когда следует развертывать контейнеры Windows в службе контейнеров Azure (т. е. Kubernetes)

Служба контейнеров Azure оптимизирует настройку популярных средств и технологий с открытым кодом специально для Azure. Вы получаете открытое решение, которое обеспечивает переносимость как для контейнеров, так и для конфигурации приложения. Вы выбрали размер, число узлов и средства Orchestrator. Служба контейнеров Azure обрабатывает инфраструктуру.

Если вы уже работаете с оркестрации с открытым кодом, например Kubernetes, Docker Swarm или DC/OS, вам не нужно изменять существующие методы управления для перемещения рабочих нагрузок контейнера в облако. Используйте средства управления приложениями, с которыми вы уже знакомы, и подключитесь через стандартные конечные точки API для вашей программы Orchestrator по своему усмотрению.

Все эти оркестрации являются зрелыми средами, если вы используете контейнеры DOCKER для Linux, но они могут находиться только в состоянии предварительной версии для контейнеров Windows.

Например, в Kubernetes поддержка контейнеров является собственной (членом-членом первого класса), поэтому использование контейнеров Windows в Kubernetes также эффективно (в предварительной версии в ACS в начале 2018).

Важное замечание. Эволюция и более подробная версия службы ACS (служба контейнеров Azure) для Kubernetes — AKS (служба Azure Kubernetes), однако контейнеры Windows по-прежнему не поддерживаются в Q2 2018, но скоро они будут поддерживаться.

>[!div class="step-by-step"]
>[Назад](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Вперед](choosing-azure-compute-options-for-container-based-applications.md)
