---
title: Использование команд Windows PowerShell в DockerFile для установки контейнеры Windows (Docker standard на основе)
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 48af11117ec8eb0034d9557a332b89d3418d4b31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567862"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Использование команд Windows PowerShell в DockerFile для установки контейнеры Windows (Docker standard на основе)

С [контейнеры Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), можно преобразовать существующие приложения Windows для образов Docker и развертывать их с помощью тех же средств, что и остальная часть экосистеме Docker.

Чтобы использовать контейнеры Windows, необходимо просто создавать команды Windows PowerShell в DockerFile, как показано в следующем примере:

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

В этом случае мы используем Windows PowerShell для установки базового образа Windows Server Core, а также службы IIS.

Аналогичным образом, можно также выполнить команды Windows PowerShell для настройки дополнительных компонентов, как традиционные ASP.NET 4.x и .NET 4.6 или любые другие программное обеспечение Windows, как показано ниже:

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
[Предыдущие] (visual-studio Сервис для docker.md) [Далее] (.. /docker-devops-workflow/index.MD)
