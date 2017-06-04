---
title: "HTTP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "протоколы, HTTP"
  - "отправка данных, HTTP"
  - "класс HttpWebResponse, отправка и получение данных"
  - "HTTP"
  - "получение данных, HTTP"
  - "протоколы приложений, HTTP"
  - "Интернет, HTTP"
  - "сетевые ресурсы, HTTP"
  - "HTTP, о HTTP"
  - "класс HttpWebRequest, отправка и получение данных"
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# HTTP
Платформа .NET Framework обеспечивает полную поддержку протокола HTTP, составляющих большая часть всего интернет\-трафика с классами <xref:System.Net.HttpWebRequest> и <xref:System.Net.HttpWebResponse>.  Эти классы, производные от <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, возвращаемый по умолчанию, когда статический метод <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> обнаруживает универсальный код ресурса \(uri\) начинаться с "HTTP" или "HTTPs".  В большинстве случаев классы **WebRequest** и **WebResponse** предоставляют все, что требуется для создания запроса, но если необходим доступ к функциям, предоставляемым Http\- определенного как свойства, то можно предоставить подходящую роль этим классам в **HttpWebRequest** или **HttpWebResponse**.  
  
 **HttpWebRequest** и **HttpWebResponse** инкапсулируют стандартная транзакция запрос\-и\- ответа HTTP, и обеспечивает доступ к общим заголовок HTTP.  Эти классы также поддерживают наиболее HTTP 1.1, в том числе конвейеризация функций, отправляющее и принимающее данные в блоках, проверке подлинности, предварительная проверка подлинности, шифровании, поддержке прокси\-сервера проверке сертификата сервера и управлении соединения.  Пользовательские заголовки, предоставляемые через свойства и заголовки не могут храниться внутри и получать доступ через свойство **Заголовки**.  
  
 **HttpWebRequest** класс по умолчанию, используемый **WebRequest** и не должны быть зарегистрированы до того, можно передать методу **WebRequest.Create** универсальный код ресурса \(uri\).  
  
 Это можно сделать приложение за HTTP перенаправите автоматически путем задания свойства <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> к **true** \(по умолчанию\).  Приложения перенаправляет запросы, а свойство [ResponseURI](frlrfsystemnethttpwebresponseclassresponseuritopic)**HttpWebResponse** будет содержать действительный интернет\-ресурс, ответил на запрос.  Если набор **AllowAutoRedirect** к **false**, приложение должно быть способно обработать перенаправите как ошибки протокола HTTP.  
  
 Приложения получают ошибки протокола HTTP, перехватывая <xref:System.Net.WebException> с <xref:System.Net.WebException.Status%2A> присваивается [WebExceptionStatus.ProtocolError](frlrfsystemnetwebexceptionstatusclasstopic).  Свойство <xref:System.Net.WebException.Response%2A> содержит **WebResponse**, отправленное сервером и указывает фактическую столкнутую ошибку HTTP.  
  
## См. также  
 [Доступ к Интернету через прокси\-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Практическое руководство. Доступ к свойствам, относящимся с HTTP](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)