---
title: Для какой ОС использовать контейнеры .NET
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Для какой ОС использовать контейнеры .NET
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: b2ae1d2e732f152133dd8a8757b955e05cdd88eb
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45970829"
---
# <a name="what-os-to-target-with-net-containers"></a>Для какой ОС использовать контейнеры .NET

Учитывая разнообразие операционных систем, поддерживаемых Docker, и различия между .NET Framework и .NET Core, следует выбирать определенные ОС и определенные версии в зависимости от платформы, которую вы используете.

Для Windows можно использовать Windows Server Core или Windows Nano Server. Эти версии Windows предоставляют разные особенности (IIS в Windows Server Core или резидентный веб-сервер, такой как Kestrel, в Nano Server), которые могут быть необходимы в .NET Framework или .NET Core соответственно.

Для Linux доступно и поддерживается множество дистрибутивов в официальных образах Docker .NET (например, Debian).

На рисунке 3-1 представлены возможные версии операционной системы в зависимости от используемой платформы .NET.

![При развертывании устаревших приложений .NET Framework выберите в качестве целевой ОС Windows Server Core, которая совместима с устаревшими приложениями и службами IIS, и образ которой имеет больший размер. При развертывании приложений .NET Core в качестве целевой ОС можно выбрать Windows Nano Server, которая оптимизирована для облака, использует Kestrel, имеет образ меньшого размера и запускается быстрее. В качестве целевой среды можно выбрать ОС Linux, которая поддерживает Debian, Alpine и другие дистрибутивы. Можете также использовать образ Kestrel, который имеет меньший размер и запускается быстрее.](./media/image1.png)

**Рис. 3-1**. Выбираемые операционные системы в зависимости от версии платформы .NET

В том случае, если требуется использовать другой дистрибутив Linux или если нужен образ с версиями, не предоставляемыми Майкрософт, можно также создать собственный образ Docker. Например, можно создать образ с ASP.NET Core для работы на классической платформе .NET Framework и в Windows Server Core, что для Docker является довольно редко используемым сценарием.

При добавлении имени образа в файл Dockerfile можно выбрать операционную систему и версию в зависимости от используемого тега, как показано в следующих примерах:

<table>
<thead>
<tr class="header">
<th>Изображение</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr>
<td>microsoft/dotnet:2.1-runtime</td>
<td>.NET core 2.1 (мультиархитектурный): поддерживает Linux и Windows Nano Server в зависимости от узла Docker.</td>
</tr>
<tr class="odd">
<td>microsoft/dotnet:2.1-aspnetcore-runtime</td>
<td><p>ASP.NET Core 2.1 (мультиархитектурный): поддерживает Linux и Windows Nano Server в зависимости от узла Docker.</p>
<p>Образ aspnetcore имеет несколько оптимизаций для ASP.NET Core.</p></td>
</tr>
<tr class="even">
<td>microsoft/dotnet:2.1-aspnetcore-runtime-alpine</td>
<td>.NET Core 2.1 (только для среды выполнения), основанный на дистрибутиве Alpine Linux</td>
</tr>
<tr class="odd">
<td>microsoft/dotnet:2.1-aspnetcore-runtime-nanoserver-1803</td>
<td>.NET Core 2.1 (только для среды выполнения), основанный на Windows Nano Server (Windows Server версии 1803)</td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
[Назад](container-framework-choice-factors.md)
[Вперед](official-net-docker-images.md)
