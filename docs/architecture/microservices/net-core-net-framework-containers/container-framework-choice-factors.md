---
title: Таблица принятия решений. Использование платформ .NET для Docker
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Таблица принятия решений. Использование платформ .NET для Docker
ms.date: 09/11/2018
ms.openlocfilehash: 96b2750e52d64b06444b7f87dea624879f37d3d7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675821"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="6f469-104">Таблица для принятия решений. Использование платформ .NET для Docker</span><span class="sxs-lookup"><span data-stu-id="6f469-104">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="6f469-105">В таблице ниже для принятия решений приводятся сводные сведения о том, когда следует использовать .NET Framework или .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6f469-105">The following decision table summarizes whether to use .NET Framework or .NET Core.</span></span> <span data-ttu-id="6f469-106">Помните, что для контейнеров Linux требуются узлы Docker на основе Linux (виртуальные машины или серверы), а для контейнеров Windows — узлы Docker на основе Windows Server (виртуальные машины или серверы).</span><span class="sxs-lookup"><span data-stu-id="6f469-106">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f469-107">На компьютерах разработки выполняется один узел Docker: Linux или Windows.</span><span class="sxs-lookup"><span data-stu-id="6f469-107">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="6f469-108">Все связанные микрослужбы, которые должны запускаться и тестироваться вместе в рамках одного решения, должны выполняться на одной платформе контейнеров.</span><span class="sxs-lookup"><span data-stu-id="6f469-108">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="6f469-109"><strong>Архитектура или тип приложения</strong></span><span class="sxs-lookup"><span data-stu-id="6f469-109"><strong>Architecture / App Type</strong></span></span></th>
<th><span data-ttu-id="6f469-110"><strong>Контейнеры Linux</strong></span><span class="sxs-lookup"><span data-stu-id="6f469-110"><strong>Linux containers</strong></span></span></th>
<th><span data-ttu-id="6f469-111"><strong>Контейнеры Windows</strong></span><span class="sxs-lookup"><span data-stu-id="6f469-111"><strong>Windows Containers</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6f469-112">Микрослужбы в контейнерах</span><span class="sxs-lookup"><span data-stu-id="6f469-112">Microservices on containers</span></span></td>
<td><span data-ttu-id="6f469-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-113">.NET Core</span></span></td>
<td><span data-ttu-id="6f469-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-114">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f469-115">Монолитные приложения</span><span class="sxs-lookup"><span data-stu-id="6f469-115">Monolithic app</span></span></td>
<td><span data-ttu-id="6f469-116">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-116">.NET Core</span></span></td>
<td><p><span data-ttu-id="6f469-117">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f469-117">.NET Framework</span></span></p>
<p><span data-ttu-id="6f469-118">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-118">.NET Core</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f469-119">Достижение высочайшей производительности и масштабируемости</span><span class="sxs-lookup"><span data-stu-id="6f469-119">Best-in-class performance and scalability</span></span></td>
<td><span data-ttu-id="6f469-120">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-120">.NET Core</span></span></td>
<td><span data-ttu-id="6f469-121">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-121">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f469-122">Перенос имеющихся (устаревших) приложений Windows Server в контейнеры</span><span class="sxs-lookup"><span data-stu-id="6f469-122">Windows Server legacy app ("brown-field") migration to containers</span></span></td>
<td>--</td>
<td><span data-ttu-id="6f469-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f469-123">.NET Framework</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f469-124">Разработка новых приложений на основе контейнеров (с нуля)</span><span class="sxs-lookup"><span data-stu-id="6f469-124">New container-based development ("green-field")</span></span></td>
<td><span data-ttu-id="6f469-125">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-125">.NET Core</span></span></td>
<td><span data-ttu-id="6f469-126">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-126">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f469-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-127">ASP.NET Core</span></span></td>
<td><span data-ttu-id="6f469-128">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-128">.NET Core</span></span></td>
<td><p><span data-ttu-id="6f469-129">.NET Core (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="6f469-129">.NET Core (recommended)</span></span></p>
<p><span data-ttu-id="6f469-130">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f469-130">.NET Framework</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f469-131">ASP.NET 4 (MVC 5, веб-API 2 и веб-формы)</span><span class="sxs-lookup"><span data-stu-id="6f469-131">ASP.NET 4 (MVC 5, Web API 2, and Web Forms)</span></span></td>
<td>--</td>
<td><span data-ttu-id="6f469-132">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f469-132">.NET Framework</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f469-133">Службы SignalR</span><span class="sxs-lookup"><span data-stu-id="6f469-133">SignalR services</span></span></td>
<td><span data-ttu-id="6f469-134">.NET Core 2.1 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6f469-134">.NET Core 2.1 or higher version</span></span></td>
<td><p><span data-ttu-id="6f469-135">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f469-135">.NET Framework</span></span></p>
<p><span data-ttu-id="6f469-136">.NET Core 2.1 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6f469-136">.NET Core 2.1 or higher version</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6f469-137">WCF, WF и другие устаревшие платформы</span><span class="sxs-lookup"><span data-stu-id="6f469-137">WCF, WF, and other legacy frameworks</span></span></td>
<td><span data-ttu-id="6f469-138">WCF в .NET Core (только клиентская библиотека WCF)</span><span class="sxs-lookup"><span data-stu-id="6f469-138">WCF in .NET Core (only the WCF client library)</span></span></td>
<td><p><span data-ttu-id="6f469-139">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f469-139">.NET Framework</span></span></p>
<p><span data-ttu-id="6f469-140">WCF в .NET Core (только клиентская библиотека WCF)</span><span class="sxs-lookup"><span data-stu-id="6f469-140">WCF in .NET Core (only the WCF client library)</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6f469-141">Использование служб Azure</span><span class="sxs-lookup"><span data-stu-id="6f469-141">Consumption of Azure services</span></span></td>
<td><p><span data-ttu-id="6f469-142">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-142">.NET Core</span></span></p>
<p><span data-ttu-id="6f469-143">(В конечном итоге все службы Azure будут предоставлять клиентские пакеты SDK для .NET Core)</span><span class="sxs-lookup"><span data-stu-id="6f469-143">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
<td><p><span data-ttu-id="6f469-144">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f469-144">.NET Framework</span></span></p>
<p><span data-ttu-id="6f469-145">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6f469-145">.NET Core</span></span></p>
<p><span data-ttu-id="6f469-146">(В конечном итоге все службы Azure будут предоставлять клиентские пакеты SDK для .NET Core)</span><span class="sxs-lookup"><span data-stu-id="6f469-146">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
><span data-ttu-id="6f469-147">[Назад](net-framework-container-scenarios.md)
>[Вперед](net-container-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="6f469-147">[Previous](net-framework-container-scenarios.md)
[Next](net-container-os-targets.md)</span></span>
