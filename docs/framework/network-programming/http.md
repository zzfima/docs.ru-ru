---
title: HTTP
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
ms.openlocfilehash: c8c799a50e5d63bbf411c338eb9e93f85a942bb0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048011"
---
# <a name="http"></a>HTTP
Платформа .NET предоставляет полную поддержку протокола HTTP, на который приходит большая часть интернет-трафика, с помощью классов <xref:System.Net.HttpWebRequest> и <xref:System.Net.HttpWebResponse>. Эти классы, производные от <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, возвращаются по умолчанию всякий раз, когда статический метод <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> обнаруживает URI, начинающийся с "http" или "https". В большинстве случаев классы **WebRequest** и **WebResponse** предоставляют все необходимое для выполнения запроса, но если вам необходим доступ к возможностям HTTP-протокола, представленным в виде свойств, можно выполнить приведение этих классов к **HttpWebRequest** или **HttpWebResponse**.  
  
 Классы **HttpWebRequest** и **HttpWebResponse** инкапсулируют стандартную транзакцию "запрос-ответ" HTTP и предоставляют доступ к основным заголовкам HTTP. Эти классы также поддерживают большинство функций HTTP 1.1, включая конвейеризацию, отправку и получение данных в блоках, проверку подлинности, предварительную проверку подлинности, шифрование, поддержку прокси-сервера, проверку сертификата сервера и управление соединениями. Пользовательские заголовки и заголовки, доступ к которым через свойства не предоставляется, можно получить в разделе **Заголовки**.  
  
 Класс **HttpWebRequest** — класс по умолчанию, который используется классом **WebRequest**. Этот класс не требуется регистрировать перед тем, как передавать URI в метод **WebRequest.Create**.  
  
 Чтобы приложение автоматически перенаправляло запросы HTTP, можно установить свойство <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> в значение **true** (по умолчанию). Приложение будет перенаправлять запросы, а свойство <xref:System.Net.HttpWebResponse.ResponseUri%2A> объекта **HttpWebResponse** будет содержать веб-ресурс, который ответил на запрос. Если установить свойство **AllowAutoRedirect** в значение **false**, приложение сможет обрабатывать перенаправления как ошибки протокола HTTP.  
  
 Приложения получают ошибки протокола HTTP, перехватывая <xref:System.Net.WebException> со свойством <xref:System.Net.WebException.Status%2A>, установленным в значение <xref:System.Net.WebExceptionStatus>. Свойство <xref:System.Net.WebException.Response%2A> означает фактическую обнаруженную ошибку HTTP и содержит объект **WebResponse**, отправленный сервером.  
  
## <a name="see-also"></a>См. также раздел

- [Доступ к Интернету через прокси-сервер](accessing-the-internet-through-a-proxy.md)
- [Использование протоколов приложений](using-application-protocols.md)
- [Практическое руководство. Доступ к свойствам, относящимся с HTTP](how-to-access-http-specific-properties.md)
