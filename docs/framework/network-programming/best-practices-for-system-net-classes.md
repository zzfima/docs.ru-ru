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
ms.openlocfilehash: c7324dcbc27c95c7d799592700d46c195e7d952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048894"
---
# <a name="best-practices-for-systemnet-classes"></a>Рекомендации по использованию классов System.Net
В этом разделе приводятся рекомендации по наиболее эффективному использованию классов, содержащихся в <xref:System.Net>:  
  
- Рекомендации по протоколу TLS см. в разделе [Рекомендации по использованию протокола TLS с .NET Framework](tls.md).

- По возможности рекомендуется всегда использовать <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> вместо приведения типов к классам потомков. Приложения, использующие **WebRequest** и **WebResponse**, могут использовать преимущества новых протоколов Интернета, не требуя при этом серьезного изменения кода.  
  
- При написании приложений ASP.NET, которые выполняются на сервере с использованием классов **System.Net**, с точки зрения производительности зачастую лучше использовать асинхронные методы для <xref:System.Net.WebRequest.GetResponse%2A> и <xref:System.Net.WebResponse.GetResponseStream%2A>.  
  
- Число открытых подключений к интернет-ресурсам может заметно влиять на производительность и пропускную способность сети. В **System.Net** по умолчанию используется два подключения для каждого приложения на один ведущий узел. С помощью свойства <xref:System.Net.ServicePoint.ConnectionLimit%2A> в <xref:System.Net.ServicePoint> приложения можно увеличить число его подключений для конкретного узла. Свойство <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> позволяет увеличить это значение по умолчанию для всех узлов.  
  
- При написании протоколов уровня сокета по возможности используйте <xref:System.Net.Sockets.TcpClient> или <xref:System.Net.Sockets.UdpClient> вместо прямого использования <xref:System.Net.Sockets.Socket>. Эти два клиентских класса инкапсулируют создание сокетов TCP и UDP, не требуя от вас обработки сведений о подключении.  
  
- При доступе к узлам, требующим ввода учетных данных, используйте класс <xref:System.Net.CredentialCache> для создания кэша учетных данных вместо того, чтобы предоставлять их с каждым запросом. Класс **CredentialCache** выполняет поиск соответствующих запросу учетных данных в кэше, освобождая вас от необходимости создавать и предоставлять учетные данные на основе URL.  
  
## <a name="see-also"></a>См. также раздел

- [Сетевое программирование в .NET Framework](index.md)
