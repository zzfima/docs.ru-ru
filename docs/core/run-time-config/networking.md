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
# <a name="run-time-configuration-options-for-networking"></a>Параметры конфигурации времени выполнения для сети

## <a name="http2-protocol"></a>Протокол HTTP/2

- Указывает, включена ли поддержка протокола HTTP/2.
- По умолчанию: отключено (`false`).
- Представлено в .NET Core 3.0.

| | Имя параметра | Значения |
| - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` — отключено<br/>`true` — включено |
| **Переменная среды** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` — отключено<br/>`1` — включено |

## <a name="sockets-http-handler"></a>Обработчик HTTP-данных для сокетов

- Указывает, используют ли высокоуровневые API сети, такие как <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> или реализацию <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> на основе [libcurl](https://curl.haxx.se/libcurl/).
- По умолчанию: используется <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).
- Этот параметр можно настроить программно, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler><br/>`false` — позволяет использовать <xref:System.Net.Http.HttpClientHandler> |
| **Переменная среды** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` — позволяет использовать <xref:System.Net.Http.SocketsHttpHandler><br/>`0` — позволяет использовать <xref:System.Net.Http.HttpClientHandler> |
