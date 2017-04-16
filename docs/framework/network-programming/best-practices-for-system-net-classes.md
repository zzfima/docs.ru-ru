---
title: "Рекомендации по использованию классов System.Net | Microsoft Docs"
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
  - "отправка данных, рекомендации"
  - "запрос данных из Интернета, рекомендации"
  - "Класс WebRequest, рекомендации"
  - "запросы данных, рекомендации"
  - "Класс WebResponse, рекомендации"
  - "рекомендации, запросы данных"
  - "получение данных, рекомендации"
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Рекомендации по использованию классов System.Net
Следующие рекомендации помогут использовать классы, содержащиеся в <xref:System.Net> к самому лучшему их преимуществу:  
  
-   Используйте <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, когда возможный вместо типа результирующие классы, являющиеся потомками.  Приложения, использующие **WebRequest** и **WebResponse** могут воспользоваться преимуществами новых протоколов Интернета детально код не изменяются.  
  
-   При написании приложения ASP.NET, которые выполняются на сервере с помощью классов **System.Net**, зачастую лучше, с точки зрения производительности для использования асинхронных методов для <xref:System.Net.WebRequest.GetResponse%2A> и <xref:System.Net.WebResponse.GetResponseStream%2A>.  
  
-   Число открытых подключений к интернет\-ресурсу может иметь огромное повлияет на сетевой производительности и пропускной способности.  **System.Net** 2 в приложение использует подключения по умолчанию основного приложения.  Установив свойство <xref:System.Net.ServicePoint.ConnectionLimit%2A> в <xref:System.Net.ServicePoint> приложения может увеличить этот номер для заданного узла.  Установив свойство <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=fullName> может увеличить это значение по умолчанию для всех узлов.  
  
-   При написании протоколы гнездо\- уровня, попробуйте использовать [TCPClient](frlrfsystemnetsocketstcpclientclasstopic) или [UDPClient](frlrfsystemnetsocketsudpclientclasstopic), когда возможный вместо записи непосредственно в <xref:System.Net.Sockets.Socket>.  Эти классы инкапсулируют создание 2 клиентов TCP и UDP\-сокет, не требуя его отрегулировали сведения о соединении.  
  
-   При обращении к сайты, которые требуют учетных данных используйте класс <xref:System.Net.CredentialCache> чтобы создать кэш учетных данных, а не указывая их с каждым запросом.  Класс **CredentialCache** ищет в кэш, чтобы найти соответствующие учетные данные для представления с автоматически создать запрос, сбрасывая ответственности и представления учетных данных на основе url\-адреса.  
  
## См. также  
 [Сетевое программирование в .NET Framework](../../../docs/framework/network-programming/index.md)