---
title: Использование команд Windows PowerShell в DockerFile для установки контейнеры Windows (Docker standard на основе)
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: d68378a12a16dd4072b381f00241e781b40c3e16
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105554"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="d3dbe-103">Использование команд Windows PowerShell в DockerFile для установки контейнеры Windows (Docker standard на основе)</span><span class="sxs-lookup"><span data-stu-id="d3dbe-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="d3dbe-104">С [контейнеры Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), можно преобразовать существующие приложения Windows для образов Docker и развертывать их с помощью тех же средств, что и остальная часть экосистеме Docker.</span><span class="sxs-lookup"><span data-stu-id="d3dbe-104">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="d3dbe-105">Чтобы использовать контейнеры Windows, необходимо просто создавать команды Windows PowerShell в DockerFile, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d3dbe-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="d3dbe-106">В этом случае мы используем Windows PowerShell для установки базового образа Windows Server Core, а также службы IIS.</span><span class="sxs-lookup"><span data-stu-id="d3dbe-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="d3dbe-107">Аналогичным образом, можно также выполнить команды Windows PowerShell для настройки дополнительных компонентов, как традиционные ASP.NET 4.x и .NET 4.6 или любые другие программное обеспечение Windows, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="d3dbe-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="d3dbe-108">[Назад](visual-studio-tools-for-docker.md)
[Вперед](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="d3dbe-108">[Previous](visual-studio-tools-for-docker.md)
[Next](../docker-devops-workflow/index.md)</span></span>
