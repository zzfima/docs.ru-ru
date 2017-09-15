---
title: "Рекомендации по использованию классов System.Net"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4fb997efc1ba23620cad4a63bd7fa683020a9056
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="best-practices-for-systemnet-classes"></a>Рекомендации по использованию классов System.Net
В этом разделе приводятся рекомендации по наиболее эффективному использованию классов, содержащихся в <xref:System.Net>:  
  
-   По возможности рекомендуется всегда использовать <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> вместо приведения типов к классам потомков. Приложения, использующие **WebRequest** и **WebResponse**, могут использовать преимущества новых протоколов Интернета, не требуя при этом серьезного изменения кода.  
  
-   При написании приложений ASP.NET, которые выполняются на сервере с использованием классов **System.Net**, с точки зрения производительности зачастую лучше использовать асинхронные методы для <xref:System.Net.WebRequest.GetResponse%2A> и <xref:System.Net.WebResponse.GetResponseStream%2A>.  
  
-   Число открытых подключений к интернет-ресурсам может заметно влиять на производительность и пропускную способность сети. В **System.Net** по умолчанию используется два подключения для каждого приложения на один ведущий узел. С помощью свойства <xref:System.Net.ServicePoint.ConnectionLimit%2A> в <xref:System.Net.ServicePoint> приложения можно увеличить число его подключений для конкретного узла. Свойство <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=fullName> позволяет увеличить это значение по умолчанию для всех узлов.  
  
-   При написании протоколов уровня сокета по возможности используйте <xref:System.Net.Sockets.TcpClient> или <xref:System.Net.Sockets.UdpClient> вместо прямого использования <xref:System.Net.Sockets.Socket>. Эти два клиентских класса инкапсулируют создание сокетов TCP и UDP, не требуя от вас обработки сведений о подключении.  
  
-   При доступе к узлам, требующим ввода учетных данных, используйте класс <xref:System.Net.CredentialCache> для создания кэша учетных данных вместо того, чтобы предоставлять их с каждым запросом. Класс **CredentialCache** выполняет поиск соответствующих запросу учетных данных в кэше, освобождая вас от необходимости создавать и предоставлять учетные данные на основе URL.  
  
## <a name="see-also"></a>См. также  
 [Сетевое программирование в .NET Framework](../../../docs/framework/network-programming/index.md)

