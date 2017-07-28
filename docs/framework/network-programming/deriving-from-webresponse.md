---
title: "Наследование от класса WebResponse | Microsoft Docs"
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
  - "Наследование от класса WebResponse"
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Наследование от класса WebResponse
Класс <xref:System.Net.WebResponse> абстрактный базовый класс, который предоставляет основные методы и свойства для создания ответа протокол\- в соответствии с конкретным, модель платформы .NET Framework подключаемый протокол.  Приложения, использующие класс <xref:System.Net.WebRequest> для запроса данных из ресурсов получать ответы в **WebResponse**.  Потомки **WebResponse** определенного Протокол\- должны реализовать абстрактные члены класса **WebResponse**.  
  
 Связанный класс **WebRequest** должен создать потомки **WebResponse**.  Например, экземпляры <xref:System.Net.HttpWebResponse> созданы только в результате вызова <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=fullName> или <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=fullName>.  Каждое **WebResponse** содержит результат выполнения запроса к ресурсу, и он не предназначен для повторного использования.  
  
## Свойство ContentLength  
 Свойство <xref:System.Net.WebResponse.ContentLength%2A> указывает число байтов данных, доступных из потока, возвращаемого методом <xref:System.Net.WebResponse.GetResponseStream%2A>.  Свойство **ContentLength** не указывает количество байтов заголовка или метаданных, возвращаемых сервером; он указывает только количество самого байт данных в ресурсе.  
  
## Свойство ContentType  
 Любое специальное свойство <xref:System.Net.WebResponse.ContentType%2A> предоставляет сведения, что протокол требует отправить клиенту, чтобы определить тип содержимого отправляемых сервером.  Обычно это тип содержимого MIME всех возвращенных данных.  
  
## Свойство заголовков  
 Свойство <xref:System.Net.WebResponse.Headers%2A> содержащего произвольную коллекцию пар имя\/значение метаданных, связанных с ответом.  Все метаданные, необходимые протоколом, можно выразить в виде пар "имя\-значение" можно включить в свойстве **Заголовки**.  
  
 Не требуется использовать свойство **Заголовки** для использования метаданных заголовка.  Метаданные для конкретного Протокол\- предоставляемых как свойства; например, свойство <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=fullName> предоставляет заголовок HTTP **Last\-Modified**.  Если метаданные заголовка которому предоставляется как свойство, не следует разрешать одно и то же свойство, которое нужно задать, используя свойство **Заголовки**.  
  
## Свойство ResponseUri  
 Свойство <xref:System.Net.WebResponse.ResponseUri%2A> содержит универсальный код ресурса \(uri\) ресурса, который фактически, ответ.  Для протоколов, которые не поддерживают перенаправления **ResponseUri** будет таким же, как свойство <xref:System.Net.WebRequest.RequestUri%2A>**WebRequest**, которая создала ответ.  Если протокол поддерживает перенаправить запрос, **ResponseUri** содержит универсальный код ресурса \(uri\) ответа.  
  
## Закройте метод  
 Метод <xref:System.Net.WebResponse.Close%2A> закрывает все производимые в запросе и ответе и очищает ресурсы, используемые запросом.  Метод **Закрыть** закрывает все экземпляры потока, используемых запросом, но не выдает исключение, если поток ответа был ранее закрыть вызовом метода <xref:System.IO.Stream.Close%2A?displayProperty=fullName>.  
  
## Метод GetResponseStream  
 Метод <xref:System.Net.WebResponse.GetResponseStream%2A> возвращает поток, содержащий ответ от запрошенного ресурса.  Поток ответа содержит только данные, возвращенные ресурсом; все заголовок или метаданных, включенные в ответе должны быть удаляются из ответа и предоставлены в приложение через свойства протокол\- определенной или свойство **Заголовки**.  
  
 Экземпляр потока возвращенный методом **GetResponseStream** принадлежит приложением и может быть закрыть, не закрывая **WebResponse**.  По соглашению вызова метода **WebResponse.Close** также закрывает поток, возвращенный **GetResponse**.  
  
## См. также  
 <xref:System.Net.WebResponse>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.FileWebResponse>   
 [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [Наследование от WebResponse](../../../docs/framework/network-programming/deriving-from-webrequest.md)