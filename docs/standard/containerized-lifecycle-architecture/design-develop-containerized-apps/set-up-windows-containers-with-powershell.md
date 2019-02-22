---
title: Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)
description: Узнайте, как с помощью PowerShell при работе с Docker в контейнерах Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: d9c0bc28f62d44eb7471b99c63055ef43da12a69
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664709"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)

С помощью [контейнеры Windows](/virtualization/windowscontainers/about/index), можно преобразовать существующие приложения Windows для образов Docker и развертывать их с помощью тех же средств, что и остальную часть экосистемы Docker.

Чтобы использовать контейнеры Windows, необходимо просто написать команды Windows PowerShell в DockerFile, как показано в следующем примере:

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

В этом случае мы используем Windows PowerShell для установки базового образа Windows Server Core, а также служб IIS.

Аналогичным образом, вы также может использовать команды Windows PowerShell для настройки дополнительных компонентов, таких как традиционные модели ASP.NET 4.x и .NET 4.6 или любое другое Windows программное обеспечение, как показано ниже:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Назад](visual-studio-tools-for-docker.md)
>[Вперед](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
