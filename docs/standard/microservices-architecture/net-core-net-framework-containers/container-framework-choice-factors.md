---
title: Таблица принятия решений. Использование платформ .NET для Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Таблица принятия решений. Использование платформ .NET для Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: 74b3749077fdb375f84ddacd98221aa4afcf2f67
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47401242"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Таблица для принятия решений. Использование платформ .NET для Docker

В таблице ниже для принятия решений приводятся сводные сведения о том, когда следует использовать .NET Framework или .NET Core. Помните, что для контейнеров Linux требуются узлы Docker на основе Linux (виртуальные машины или серверы), а для контейнеров Windows — узлы Docker на основе Windows Server (виртуальные машины или серверы).

> [!IMPORTANT]
> На компьютерах разработки выполняется один узел Docker: Linux или Windows. Все связанные микрослужбы, которые должны запускаться и тестироваться вместе в рамках одного решения, должны выполняться на одной платформе контейнеров.

<table>
<thead>
<tr class="header">
<th><strong>Архитектура или тип приложения</strong></th>
<th><strong>Контейнеры Linux</strong></th>
<th><strong>Контейнеры Windows</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Микрослужбы в контейнерах</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>Монолитные приложения</td>
<td>.NET Core</td>
<td><p>.NET Framework</p>
<p>.NET Core</p></td>
</tr>
<tr class="odd">
<td>Достижение высочайшей производительности и масштабируемости</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>Перенос имеющихся (устаревших) приложений Windows Server в контейнеры</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="odd">
<td>Разработка новых приложений на основе контейнеров (с нуля)</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>ASP.NET Core</td>
<td>.NET Core</td>
<td><p>.NET Core (рекомендуется)</p>
<p>.NET Framework</p></td>
</tr>
<tr class="odd">
<td>ASP.NET 4 (MVC 5, веб-API 2 и веб-формы)</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="even">
<td>Службы SignalR</td>
<td>.NET Core 2.1 или более поздней версии</td>
<td><p>.NET Framework</p>
<p>.NET Core 2.1 или более поздней версии</p></td>
</tr>
<tr class="odd">
<td>WCF, WF и другие устаревшие платформы</td>
<td>WCF в .NET Core (только клиентская библиотека WCF)</td>
<td><p>.NET Framework</p>
<p>WCF в .NET Core (только клиентская библиотека WCF)</p></td>
</tr>
<tr class="even">
<td>Использование служб Azure</td>
<td><p>.NET Core</p>
<p>(В конечном итоге все службы Azure будут предоставлять клиентские пакеты SDK для .NET Core)</p></td>
<td><p>.NET Framework</p>
<p>.NET Core</p>
<p>(В конечном итоге все службы Azure будут предоставлять клиентские пакеты SDK для .NET Core)</p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
[Назад](net-framework-container-scenarios.md)
[Вперед](net-container-os-targets.md)
