---
title: Параметры конфигурации сети
description: Сведения о параметрах времени выполнения, определяющих использование сети для приложений .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 622c4afbd36d3d9004edbd9219145fa9e5d326ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74998837"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="bf7d3-103">Параметры конфигурации времени выполнения для сети</span><span class="sxs-lookup"><span data-stu-id="bf7d3-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="bf7d3-104">Протокол HTTP/2</span><span class="sxs-lookup"><span data-stu-id="bf7d3-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="bf7d3-105">Указывает, включена ли поддержка протокола HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="bf7d3-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="bf7d3-106">По умолчанию: отключено (`false`).</span><span class="sxs-lookup"><span data-stu-id="bf7d3-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="bf7d3-107">Представлено в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="bf7d3-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="bf7d3-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bf7d3-108">Setting name</span></span> | <span data-ttu-id="bf7d3-109">Значения</span><span class="sxs-lookup"><span data-stu-id="bf7d3-109">Values</span></span> |
| - | - |
| <span data-ttu-id="bf7d3-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bf7d3-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="bf7d3-111">`false` — отключено</span><span class="sxs-lookup"><span data-stu-id="bf7d3-111">`false` - disabled</span></span><br/><span data-ttu-id="bf7d3-112">`true` — включено</span><span class="sxs-lookup"><span data-stu-id="bf7d3-112">`true` - enabled</span></span> |
| <span data-ttu-id="bf7d3-113">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bf7d3-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="bf7d3-114">`0` — отключено</span><span class="sxs-lookup"><span data-stu-id="bf7d3-114">`0` - disabled</span></span><br/><span data-ttu-id="bf7d3-115">`1` — включено</span><span class="sxs-lookup"><span data-stu-id="bf7d3-115">`1` - enabled</span></span> |

## <a name="sockets-http-handler"></a><span data-ttu-id="bf7d3-116">Обработчик HTTP-данных для сокетов</span><span class="sxs-lookup"><span data-stu-id="bf7d3-116">Sockets HTTP handler</span></span>

- <span data-ttu-id="bf7d3-117">Указывает, используют ли высокоуровневые API сети, такие как <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> или реализацию <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> на основе [libcurl](https://curl.haxx.se/libcurl/).</span><span class="sxs-lookup"><span data-stu-id="bf7d3-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="bf7d3-118">По умолчанию: используется <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span><span class="sxs-lookup"><span data-stu-id="bf7d3-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="bf7d3-119">Этот параметр можно настроить программно, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf7d3-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="bf7d3-120">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="bf7d3-120">Setting name</span></span> | <span data-ttu-id="bf7d3-121">Значения</span><span class="sxs-lookup"><span data-stu-id="bf7d3-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="bf7d3-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="bf7d3-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="bf7d3-123">`true` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="bf7d3-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="bf7d3-124">`false` — позволяет использовать <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="bf7d3-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="bf7d3-125">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="bf7d3-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="bf7d3-126">`1` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="bf7d3-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="bf7d3-127">`0` — позволяет использовать <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="bf7d3-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
