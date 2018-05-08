---
title: С помощью средств Visual Studio для Docker (Visual Studio в Windows)
description: Жизненный цикл контейнерного приложения Docker на основе платформы и средств Майкрософт
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 05db5cf8e8dc073dd341fbffab619c326b48f136
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>С помощью средств Visual Studio для Docker (Visual Studio в Windows)

Разработчик рабочего процесса при использовании средств Visual Studio для Docker аналогична рабочего процесса при использовании кода Visual Studio и Docker CLI (на самом деле он основан на одном Docker CLI), но проще приступить к работе, упрощает процесс и предоставляет больше производительность для построения, запуска и создать задач. Это также может выполнять и отлаживать вашей контейнеры через простые действия, такие как F5 или Ctrl + F5 в Visual Studio. Еще более с Visual Studio 2017 г Помимо возможности позволяют выполнять и отлаживать в одном контейнере, можно также запустить и отладить группы контейнеров (всего решения) в то же время, если они определены в одном файле docker compose.yml на уровне решения.

## <a name="configuring-your-local-environment"></a>Настройка локальной среде

С последними версиями Docker для Windows проще, чем когда-либо для разработки Docker приложений так, как настройка является простым, как описано в следующих документах.

**Дополнительные сведения:** Дополнительные сведения об установке Docker для Windows, перейдите к <https://docs.docker.com/docker-for-windows/>.

Если вы используете Visual Studio 2015, необходимо иметь обновления 3 или более поздней версии, а также средств Visual Studio для Docker.

**Дополнительные сведения:** инструкции по установке Visual Studio перейдите к [ https://www.visualstudio.com/\ продуктов или vs-2015--выпуски продукта](https://www.visualstudio.com/products/vs-2015-product-editions).

Для просмотра дополнительных сведений об установке набора средств Visual Studio для Docker, воспользуйтесь <http://aka.ms/vstoolsfordocker> и <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.

Вы используете Visual Studio 2017 г., уже включена поддержка Docker.

## <a name="using-docker-tools-in-visual-studio-2015"></a>С помощью средств Docker в Visual Studio 2015

Средства Visual Studio для Docker предоставляет согласованный способ разработки и проверки локально в контейнеры Docker для Linux в узле Linux Docker или виртуальной Машины или в контейнеры Windows непосредственно в Windows.

Если вы используете один контейнер, первое, что необходимо начать — включить поддержку Docker в проект .NET Core. Для этого щелкните правой кнопкой мыши файл проекта, как показано на рисунке 4 — 25.

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/image/file/205468/1/add-docker-support.png](./media/image31.png)

На рисунке 4-25: Включение поддержки Docker для проекта Visual Studio

## <a name="using-docker-tools-in-visual-studio-2017"></a>С помощью средств Docker в Visual Studio 2017 г.

При добавлении поддержки Docker в проект службы в решении (см. рис. 4-26), Visual Studio является не просто прибавляет файл DockerFile в проект, он также является добавление раздела службы в решения docker compose.yml файлы (или создании файлов, если они не существует). Это простой способ начать составление multicontainer решения; Затем можно открыть файлы docker compose.yml и обновлять их с дополнительными возможностями.

![](./media/image32.png)

Рис. 4-26: Включение поддержки Docker решений в проекте Visual Studio 2017 г.

Это действие не только добавляет файл DockerFile в проект, он также добавляет необходимую настройку строки кода для глобальных docker-compose.yml задавать на уровне решения.

Также можно включить поддержку Docker при создании проекта ASP.NET Core в Visual Studio 2017 г., как показано на рисунке 4-27.

![](./media/image33.png)

Рис. 4-27: Включение поддержки Docker при создании проекта

После добавления поддержки Docker в решение в Visual Studio, вы также увидите нового узла дерева в обозревателе решений с файлами добавлены docker-compose.yml, как показано на рисунке 4-28.

![](./media/image34.PNG)

Рис. 4-28: файлы docker compose.yml теперь отображаются в обозревателе решений

Можно развернуть multicontainer приложения с помощью файла одного docker-compose.yml при запуске docker составления вверх; Тем не менее, Visual Studio добавляет группу из них, можно изменить значения в зависимости от среды (разработки и производственной) и выполнения типа (выпуска и отладки). Эта возможность лучше описывается в последующих главах.

**Дополнительные сведения:** для получения сведений о реализации службы и использовании средств Visual Studio для Docker в следующих статьях:

Сборки, отладки, обновления и обновления приложений в локальном контейнере Docker: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Разверните контейнер ASP.NET к удаленному узлу Docker. [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)


>[!div class="step-by-step"]
[Предыдущие] (docker приложения внутреннее loop-workflow.md) [Далее] (set-up-windows-containers-with-powershell.md)
