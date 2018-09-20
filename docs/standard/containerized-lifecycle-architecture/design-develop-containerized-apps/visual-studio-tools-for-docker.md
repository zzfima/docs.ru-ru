---
title: С помощью средств Visual Studio для Docker (Visual Studio в Windows)
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: af14c92ab27885deec878dc33e7b94035f43e65b
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46488955"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>С помощью средств Visual Studio для Docker (Visual Studio в Windows)

Рабочий процесс разработки при использовании инструментов Visual Studio для Docker похоже на рабочий процесс, при использовании Visual Studio Code и Docker CLI. По сути, он основан на том же Docker CLI, но проще приступить к работе, упрощает процесс и обеспечивает повышение производительности для сборки, запуска, а также объединять задач. Он также имеет возможность выполнять и отлаживать контейнеры с помощью простых действий, таких как F5 или Ctrl + F5, из Visual Studio. Благодаря поддержке оркестрации дополнительный контейнер, помимо возможности для запуска и отладки одного контейнера можно выполнять и отлаживать группу контейнеров (всего решения), в то же время. Просто определите контейнеры в том же *docker-compose.yml* файл на уровне решения.

## <a name="configuring-your-local-environment"></a>Настройка локальной среды

Поддержка docker включена в Visual Studio 2017 с любым из рабочей нагрузки .NET и .NET Core. Установите Docker для Windows отдельно.

В последних версиях Docker для Windows это проще, чем когда-либо для разработки приложений Docker так, как настройка довольно прост, как описано в следующих документах.

**Дополнительные сведения:** Дополнительные сведения об установке Docker для Windows, перейдите к <https://docs.docker.com/docker-for-windows/>.

**Дополнительные сведения:** инструкции по установке Visual Studio, см. в статье [ https://visualstudio.microsoft.com/downloads/ ](https://visualstudio.microsoft.com/downloads/).

Чтобы просмотреть сведения об установке средств Visual Studio для Docker, перейдите к <http://aka.ms/vstoolsfordocker> и <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.

## <a name="using-docker-tools-in-visual-studio-2017"></a>С помощью средств Docker в Visual Studio 2017

При добавлении поддержки Docker в проект (см. рис. 4-26), Visual Studio добавляет *Dockerfile* в корневую папку проекта.

![Включение поддержки решения Docker в проекте Visual Studio 2017](./media/image32.png)

Рис. 4-26: Включение поддержки решения Docker в проекте Visual Studio 2017

 Поддержка оркестрации контейнера, с помощью Docker Compose, добавляется по умолчанию в Visual Studio 2017 версии 15.7 или более ранней версии. Поддержка оркестрации контейнеров — это компонент согласием в Visual Studio 2017 версии 15.8 или более поздней версии, в этом случае Docker Compose и Service Fabric поддерживаются.

С помощью Visual Studio требуется выделить 15,8 и более поздних версий можно добавить поддержку для нескольких проектов в решении, каждый из которых содержит связанный контейнер. Щелкните правой кнопкой мыши узел решения или проекта в **обозревателе решений**и выберите **добавить** > **поддержки Оркестрации контейнеров**.  Затем выберите **Docker Compose** или **Service Fabric** для управления контейнерами.

При выборе **Docker Compose**, Visual Studio добавляет раздел служб в своем решении *docker-compose.yml* файлы (или создает файлы, если они не существуют). Это простой способ начать создание многоконтейнерного решения; Затем можно открыть *docker-compose.yml* файлы и обновлять их с помощью дополнительных функций.

Это действие добавляет требуемую конфигурацию строки кода для *docker-compose.yml* задать на уровне решения.

Также можно включить поддержку Docker при создании проекта ASP.NET Core в Visual Studio 2017, как показано на рисунке 4-27.

![Включение поддержки Docker при создании проекта](./media/image33.png)

Рис. 4-27: Включение поддержки Docker при создании проекта

После добавления поддержки Docker в решение в Visual Studio, вы также увидите новый узел дерева на **обозревателе решений** путем добавления *docker-compose.yml* файлы, как показано на рис. 4-28.

![файлы docker-compose.yml, теперь отображаются в обозревателе решений](./media/image34.PNG)

Рис. 4-28: файлы docker-compose.yml отображаться **обозревателе решений**

Можно развернуть многоконтейнерного приложения с помощью одной *docker-compose.yml* файл при запуске `docker-compose up`, однако Visual Studio добавляет группу серверов, чтобы вы могли переопределять значения в зависимости от среды (разработки или для рабочей среды) и введите (выпуска или отладки) выполнения. Эта возможность лучше описан в последующих главах.

Можно также использовать Service Fabric вместо Docker Compose для управления несколькими контейнерами. См. в разделе [руководство: развертывание приложения .NET в контейнере Windows в Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-host-app-in-a-container).

**Дополнительные сведения:** Дополнительные сведения о реализации служб и использование набора средств Visual Studio для Docker в следующих статьях:

Сборки, отладки, обновления и обновления приложений в локальном контейнере Docker: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Развертывание контейнера ASP.NET Core Docker в реестр контейнеров: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[Назад](docker-apps-inner-loop-workflow.md)
[Вперед](set-up-windows-containers-with-powershell.md)
