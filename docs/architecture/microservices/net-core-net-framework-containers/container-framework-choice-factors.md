---
title: Таблица принятия решений. Использование платформ .NET для Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Таблица принятия решений. Использование платформ .NET для Docker
ms.date: 09/11/2018
ms.openlocfilehash: 8ffe2b7bc0bee976d3a63b274994dbcc8aef0c61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628323"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Таблица для принятия решений. Использование платформ .NET для Docker

В таблице ниже для принятия решений приводятся сводные сведения о том, когда следует использовать .NET Framework или .NET Core. Помните, что для контейнеров Linux требуются узлы Docker на основе Linux (виртуальные машины или серверы), а для контейнеров Windows — узлы Docker на основе Windows Server (виртуальные машины или серверы).

> [!IMPORTANT]
> На компьютерах разработки выполняется один узел Docker: Linux или Windows. Все связанные микрослужбы, которые должны запускаться и тестироваться вместе в рамках одного решения, должны выполняться на одной платформе контейнеров.

| Архитектура и тип приложения | Контейнеры Linux | Контейнеры Windows |
|-------------------------|------------------|--------------------|
| Микрослужбы в контейнерах | .NET Core | .NET Core |
| Монолитные приложения | .NET Core | .NET Framework <br/> .NET Core |
| Достижение высочайшей производительности и масштабируемости | .NET Core | .NET Core |
| Перенос имеющихся (устаревших) приложений Windows Server в контейнеры | -- | .NET Framework |
| Разработка новых приложений на основе контейнеров (с нуля) | .NET Core | .NET Core |
| ASP.NET Core | .NET Core | .NET Core (рекомендуется) <br/> .NET Framework |
| ASP.NET 4 (MVC 5, веб-API 2 и веб-формы) | -- | .NET Framework |
| Службы SignalR | .NET Core 2.1 или более поздней версии | .NET Framework <br/> .NET Core 2.1 или более поздней версии |
| WCF, WF и другие устаревшие платформы | WCF в .NET Core (только клиентская библиотека) | .NET Framework <br/> WCF в .NET Core (только клиентская библиотека) |
| Использование служб Azure | .NET Core <br/> (в конечном итоге большинство служб Azure будет предоставлять клиентские пакеты SDK для .NET Core) | .NET Framework <br/> .NET Core <br/> (в конечном итоге большинство служб Azure будет предоставлять клиентские пакеты SDK для .NET Core) |

>[!div class="step-by-step"]
>[Назад](net-framework-container-scenarios.md)
>[Вперед](net-container-os-targets.md)
