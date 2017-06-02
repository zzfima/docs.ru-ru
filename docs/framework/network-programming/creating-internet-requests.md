---
title: "Создание интернет-запросов | Microsoft Docs"
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
  - "класс WebRequest, отправка и получение данных"
  - "Сетевое взаимодействие"
  - "класс HttpWebResponse, отправка и получение данных"
  - "запрос данных из Интернета, создание запросов"
  - "Сетевые ресурсы"
  - "Интернет, запрос данных"
  - "запросы данных, создание запросов"
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Создание интернет-запросов
Приложения создают экземпляры <xref:System.Net.WebRequest> с помощью метода <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName>.  Это статический метод, который создает класс, производный от **WebRequest** на основе переданной схеме универсального кода ресурса \(uri\).  
  
## Запросы FTP и Интернет, файл  
 Платформа .NET Framework предоставляет класс, производный от <xref:System.Net.HttpWebRequest>**WebRequest**, к запросам HTTP и HTTPS.  В большинстве случаев класс **WebRequest** предоставляет все свойства нужно выполнить запрос. однако если требуется, можно привести **WebRequest** объекты, созданные методом **WebRequest.Create** к типу **HttpWebRequest** для получения доступа к свойствам Http\- определенного запроса.  Аналогично, объект **HttpWebResponse** обрабатывает ответы из запросов HTTP и HTTPS.  Для получения доступа к свойствам определенного **HttpWebResponse** Http\- объект необходимо привести объекты **WebResponse** к типу **HttpWebResponse** .  
  
 Платформа .NET Framework также предоставляет классы <xref:System.Net.FileWebRequest> и <xref:System.Net.FileWebResponse> запросы маркеров для ресурсов, использующих "файл: " Схема универсального кода ресурса \(uri\).  Кроме того, <xref:System.Net.FtpWebRequest> и классы <xref:System.Net.FtpWebResponse> на запросы маркеров для ресурсов, использующих "ftp". " схема.  Если запрос ресурса, в котором используется любой из этих схемы, можно использовать метод **WebRequest.Create** для получения объекта, с которым нужно выполнить запрос.  
  
 Для обработки запросов, использующих другие протоколы уровня приложения, необходимо реализовать определенный протокол\- классы, производные от **WebRequest**  и  **WebResponse**.  Дополнительные сведения см. в разделе [Programming Pluggable protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
## См. также  
 [Практическое руководство. Запрос данных с помощью класса WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)