---
title: "Использование команд Windows PowerShell в DockerFile для установки контейнеры Windows (Docker standard на основе)"
description: "Жизненный цикл приложений контейнерного Docker с помощью платформы Майкрософт и средств"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: f7e92b0f1c749e2c00e3afc4ffcfc2fc88d7628f
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2017
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="4d320-104">Использование команд Windows PowerShell в DockerFile для установки контейнеры Windows (Docker standard на основе)</span><span class="sxs-lookup"><span data-stu-id="4d320-104">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="4d320-105">С [контейнеры Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), можно преобразовать существующие приложения Windows для образов Docker и развертывать их с помощью тех же средств, что и остальная часть экосистеме Docker.</span><span class="sxs-lookup"><span data-stu-id="4d320-105">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="4d320-106">Чтобы использовать контейнеры Windows, необходимо просто создавать команды Windows PowerShell в DockerFile, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4d320-106">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="4d320-107">В этом случае мы используем Windows PowerShell для установки базового образа Windows Server Core, а также службы IIS.</span><span class="sxs-lookup"><span data-stu-id="4d320-107">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="4d320-108">Аналогичным образом, можно также выполнить команды Windows PowerShell для настройки дополнительных компонентов, как традиционные ASP.NET 4.x и .NET 4.6 или любые другие программное обеспечение Windows, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="4d320-108">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="4d320-109">[Предыдущие] (visual-studio Сервис для docker.md) [Далее] (.. /docker-devops-workflow/index.MD)</span><span class="sxs-lookup"><span data-stu-id="4d320-109">[Previous] (visual-studio-tools-for-docker.md) [Next] (../docker-devops-workflow/index.md)</span></span>
