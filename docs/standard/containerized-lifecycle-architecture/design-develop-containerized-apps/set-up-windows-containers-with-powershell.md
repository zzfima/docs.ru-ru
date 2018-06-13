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
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="e97f9-103">Использование команд Windows PowerShell в DockerFile для установки контейнеры Windows (Docker standard на основе)</span><span class="sxs-lookup"><span data-stu-id="e97f9-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="e97f9-104">С [контейнеры Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), можно преобразовать существующие приложения Windows для образов Docker и развертывать их с помощью тех же средств, что и остальная часть экосистеме Docker.</span><span class="sxs-lookup"><span data-stu-id="e97f9-104">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="e97f9-105">Чтобы использовать контейнеры Windows, необходимо просто создавать команды Windows PowerShell в DockerFile, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e97f9-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="e97f9-106">В этом случае мы используем Windows PowerShell для установки базового образа Windows Server Core, а также службы IIS.</span><span class="sxs-lookup"><span data-stu-id="e97f9-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="e97f9-107">Аналогичным образом, можно также выполнить команды Windows PowerShell для настройки дополнительных компонентов, как традиционные ASP.NET 4.x и .NET 4.6 или любые другие программное обеспечение Windows, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e97f9-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="e97f9-108">[Предыдущие] (visual-studio Сервис для docker.md) [Далее] (.. /docker-devops-workflow/index.MD)</span><span class="sxs-lookup"><span data-stu-id="e97f9-108">[Previous] (visual-studio-tools-for-docker.md) [Next] (../docker-devops-workflow/index.md)</span></span>
