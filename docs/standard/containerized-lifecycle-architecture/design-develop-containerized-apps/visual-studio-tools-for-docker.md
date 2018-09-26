---
title: Visual Studio Tools for Docker в Windows
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: cd140c12ef4a0187cce096e013937d5c98cd4b39
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170799"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>С помощью средств Visual Studio для Docker (Visual Studio в Windows)

Visual Studio Tools для рабочий процесс разработки Docker похоже на использование Visual Studio Code и Docker CLI (он основан на том же Docker CLI). Средства Visual Studio для Docker даже упрощает начало работы, упрощает процесс и обеспечивает повышение производительности для сборки, запуска и объединять задач. Выполнение и отладка контейнеров с помощью простых действий, таких как **F5** и **Ctrl**+**F5**.

> [!NOTE]
> Эта статья относится к Visual Studio в Windows, а не в Visual Studio для Mac.

## <a name="configure-your-local-environment"></a>Настройка локальной среды

В последних версиях Docker для Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), простой настройки упрощает процесс разработки приложений Docker.

Поддержка docker включена в Visual Studio 2017. Ссылка для загрузки Visual Studio 2017: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

## <a name="use-docker-tools-in-visual-studio-2017"></a>С помощью средств Docker в Visual Studio 2017

Существует два уровня поддержки Docker, который можно добавить в проект. В веб-приложения .NET Core проектов, можно просто добавить *Dockerfile* файл в проект, включение поддержки Docker. На следующем уровне находится поддержки оркестратора контейнеров, который добавляет *Dockerfile* в проект (если он еще не существует) и *docker-compose.yml* файл на уровне решения.

**Добавить** > **поддержку Docker** и **добавить** > **поддержки оркестратора контейнеров** команды находятся в контекстном меню (или контекстное меню) из узла проекта для проекта веб-приложения в **обозревателе решений**, как показано на рисунке 4-26:

![Добавить поддержку Docker команду меню в Visual Studio](media/add-docker-support-menu.png)

Рис. 4-26: Добавление поддержки Docker в проект Visual Studio 2017

### <a name="add-docker-support"></a>Добавление поддержки Docker

Можно добавить поддержку Docker в существующий проект веб-приложения .NET Core, выбрав **добавить** > **Docker поддерживает** в **обозревателе решений**. Можно также включить поддержку Docker во время создания проекта, выбрав **Включение поддержки Docker** в **новый веб-приложение ASP.NET Core** диалоговое окно, которое открывается при нажатии **ОК** в **новый проект** диалоговое окно, как показано на рисунке 4-27.

![Включить поддержку Docker для нового веб-приложения ASP.NET Core в Visual Studio](./media/enable-docker-support-visual-studio.png)

Рис. 4-27: Включение поддержки Docker во время создания проекта в Visual Studio 2017

При добавлении или включить поддержку Docker, Visual Studio добавляет *Dockerfile* файл в проект.

> [!NOTE]
> Когда вы включаете поддержку Docker Compose во время создания проекта для проект веб-приложения .NET Framework (не .NET Core проект веб-приложения), как показано на рис. 4-28, также добавляется поддержка оркестратора контейнеров.
>
> ![Включить Docker compose поддержка проект веб-приложения .NET Framework](media/enable-docker-compose-support.png)

> Рис. 4-28: Включение поддержки Docker Compose на веб-приложения .NET Framework проекта в Visual Studio 2017

### <a name="add-container-orchestrator-support"></a>Добавление поддержки оркестратора контейнеров

При необходимости для составления многоконтейнерного решения, добавление поддержки оркестратора контейнеров к проектам. При добавлении поддержки оркестратора контейнеров, Visual Studio добавляет *Dockerfile* к проекту (если он еще не существует), глобальный *docker-compose.yml* файл на уровне решения. Это позволяет выполнять и отлаживать группу контейнеров (всего решения) в то же время, если они определяются в том же *docker-compose.yml* файл. Если *docker-compose.yml* уже существует, Visual Studio просто добавляет необходимые строки кода конфигурации к нему.

После добавления поддержки оркестрации контейнера в проект, вы видите добавлен в проект файл Dockerfile и **docker-compose** папка добавлена в решение в **обозревателе решений**, как показано на рис. 4-29:

![Файлы docker в обозревателе решений в Visual Studio](media/docker-support-solution-explorer.png)

Рис. 4-29: файлы Docker в обозревателе решений в Visual Studio 2017

**Дополнительные сведения:** Дополнительные сведения о реализации служб и использование набора средств Visual Studio для Docker в следующих статьях:

Сборки, отладки, обновления и обновления приложений в локальном контейнере Docker: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Развертывание контейнера ASP.NET Core Docker в реестр контейнеров: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[Назад](docker-apps-inner-loop-workflow.md)
[Вперед](set-up-windows-containers-with-powershell.md)