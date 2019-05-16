---
title: Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)
description: Узнайте, как с помощью PowerShell при работе с Docker в контейнерах Windows
ms.date: 02/15/2019
ms.openlocfilehash: e91d278aef1365a111e8d67ff04092dfc6a44185
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641588"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="91411-103">Использование команд Windows PowerShell в DockerFile для настройки контейнеров Windows (на основе стандарта Docker)</span><span class="sxs-lookup"><span data-stu-id="91411-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="91411-104">С помощью [контейнеры Windows](/virtualization/windowscontainers/about/index), можно преобразовать существующие приложения Windows для образов Docker и развертывать их с помощью тех же средств, что и остальную часть экосистемы Docker.</span><span class="sxs-lookup"><span data-stu-id="91411-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="91411-105">Чтобы использовать контейнеры Windows, необходимо просто написать команды Windows PowerShell в DockerFile, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="91411-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="91411-106">В этом случае мы используем Windows PowerShell для установки базового образа Windows Server Core, а также служб IIS.</span><span class="sxs-lookup"><span data-stu-id="91411-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="91411-107">Аналогичным образом, вы также может использовать команды Windows PowerShell для настройки дополнительных компонентов, таких как традиционные модели ASP.NET 4.x и .NET 4.6 или любое другое Windows программное обеспечение, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="91411-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="91411-108">[Назад](visual-studio-tools-for-docker.md)
>[Вперед](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="91411-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
