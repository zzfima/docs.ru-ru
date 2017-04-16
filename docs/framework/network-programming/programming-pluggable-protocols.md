---
title: "Программирование подключаемых протоколов | Microsoft Docs"
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
  - "загрузка интернет-ресурсов, подключаемые протоколы"
  - "класс WebRequest, подключаемые протоколы"
  - "ответ на интернет-запрос, подключаемые протоколы"
  - "класс WebRequest, подключаемые протоколы"
  - "отправка данных, подключаемые протоколы"
  - "сетевые ресурсы, подключаемые протоколы"
  - "Интернет, подключаемые протоколы"
  - "программирование подключаемых протоколов"
  - "подключаемые протоколы, программирование"
  - "запрос данных из Интернета, подключаемые протоколы"
  - "получение данных, подключаемые протоколы"
  - "протоколы, подключаемые"
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Программирование подключаемых протоколов
Абстрактные классы предоставляют <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> основой для подключаемые протоколы.  Производными классами протокол\- от конкретного <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, приложение может запросить данные из интернет\-ресурса и чтения ответа без указания используемого протокола.  
  
 Перед созданием протокол\- специфичные <xref:System.Net.WebRequest> необходимо зарегистрировать его создать метод.  Используйте статический метод <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29><xref:System.Net.WebRequest> для регистрации является потомком <xref:System.Net.WebRequest> для обработки набор запросов к указанной схеме через интернет к схеме и к серверу или к схеме сервер и пути.  
  
 В большинстве случаев вы будете отправлять и получать данные, используя методы и свойства <xref:System.Net.WebRequest> классифицируют.  Однако при необходимости доступа к свойствам определенного протокол\-, то можно предоставить подходящую роль <xref:System.Net.WebRequest> в конкретный экземпляр производного класса.  
  
 Чтобы воспользоваться преимуществами подключаемые протоколы, потомки <xref:System.Net.WebRequest> должны быть заданы по умолчанию транзакцию запрос\-и\- ответа, которая не требует определенного свойства протокол\- установлены.  Например, класс <xref:System.Net.HttpWebRequest>, который реализует класс <xref:System.Net.WebRequest> для HTTP предоставляет используемый по умолчанию `GET` запроса и возвращает <xref:System.Net.HttpWebResponse>, содержащий поток, возвращенный из веб\-сервере.  
  
## См. также  
 [Наследование от WebResponse](../../../docs/framework/network-programming/deriving-from-webrequest.md)   
 [Наследование от класса WebResponse](../../../docs/framework/network-programming/deriving-from-webresponse.md)   
 [Сетевое программирование в .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Практическое руководство. Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом](../../../docs/framework/network-programming/how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)