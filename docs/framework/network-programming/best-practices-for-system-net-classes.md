---
title: Рекомендации по использованию классов System.Net
ms.date: 03/30/2017
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c74f9d0534675d07c87d3edbcf8434cd98f6c621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393949"
---
# <a name="best-practices-for-systemnet-classes"></a>Рекомендации по использованию классов System.Net
В этом разделе приводятся рекомендации по наиболее эффективному использованию классов, содержащихся в <xref:System.Net>:  
  
-   Рекомендации по протоколу TLS см. в разделе [Рекомендации по использованию протокола TLS с .NET Framework](tls.md).

-   По возможности рекомендуется всегда использовать <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> вместо приведения типов к классам потомков. Приложения, использующие **WebRequest** и **WebResponse**, могут использовать преимущества новых протоколов Интернета, не требуя при этом серьезного изменения кода.  
  
-   При написании приложений ASP.NET, которые выполняются на сервере с использованием классов **System.Net**, с точки зрения производительности зачастую лучше использовать асинхронные методы для <xref:System.Net.WebRequest.GetResponse%2A> и <xref:System.Net.WebResponse.GetResponseStream%2A>.  
  
-   Число открытых подключений к интернет-ресурсам может заметно влиять на производительность и пропускную способность сети. В **System.Net** по умолчанию используется два подключения для каждого приложения на один ведущий узел. С помощью свойства <xref:System.Net.ServicePoint.ConnectionLimit%2A> в <xref:System.Net.ServicePoint> приложения можно увеличить число его подключений для конкретного узла. Свойство <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> позволяет увеличить это значение по умолчанию для всех узлов.  
  
-   При написании протоколов уровня сокета по возможности используйте <xref:System.Net.Sockets.TcpClient> или <xref:System.Net.Sockets.UdpClient> вместо прямого использования <xref:System.Net.Sockets.Socket>. Эти два клиентских класса инкапсулируют создание сокетов TCP и UDP, не требуя от вас обработки сведений о подключении.  
  
-   При доступе к узлам, требующим ввода учетных данных, используйте класс <xref:System.Net.CredentialCache> для создания кэша учетных данных вместо того, чтобы предоставлять их с каждым запросом. Класс **CredentialCache** выполняет поиск соответствующих запросу учетных данных в кэше, освобождая вас от необходимости создавать и предоставлять учетные данные на основе URL.  
  
## <a name="see-also"></a>См. также  
 [Сетевое программирование в .NET Framework](../../../docs/framework/network-programming/index.md)
