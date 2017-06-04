---
title: "FTP | Microsoft Docs"
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
  - "FTP"
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# FTP
Платформа .NET Framework обеспечивает полную поддержку протокола FTP с классами <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse>.  Эти классы являются производными от <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>.  В большинстве случаев классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> предоставляют все, что требуется для создания запроса, но если необходим доступ к функциям, предоставляемым FTP\- определенной в виде свойств, то можно предоставить подходящую роль этим классам в <xref:System.Net.FtpWebRequest> или <xref:System.Net.FtpWebResponse>.  
  
## Примеры  
 Дополнительные сведения см. в разделах: [Практическое руководство. Скачивание файлов с использованием FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [Практическое руководство. Отправка файлов с использованием FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) и [Практическое руководство. Список содержимого каталога с помощью FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).  
  
## FTP и учетные записи\-посредники  
 Если прокси\-сервер \(заданный свойством <xref:System.Net.FtpWebRequest.Proxy%2A> \) прокси\-сервер HTTP, поддерживаются только <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> и команды <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.  
  
## См. также  
 [Доступ к Интернету через прокси\-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Образец технологии клиента FTP](http://go.microsoft.com/fwlink/?LinkID=179557)   
 [Образец технологии обозревателя FTP](http://go.microsoft.com/fwlink/?LinkID=179569)   
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)