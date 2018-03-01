---
title: FTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 6c0e0172bc42b0b14eebdeaba85d454c5aec25c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ftp"></a>FTP
Платформа .NET Framework обеспечивает полную поддержку протокола FTP посредством классов <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse>. Эти классы являются производными от <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>. В большинстве случаев классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> предоставляют все необходимое для выполнения запроса, но если вам требуется доступ к возможностям протокола FTP, представленным в виде свойств, можно выполнить приведение типа этих классов к <xref:System.Net.FtpWebRequest> или <xref:System.Net.FtpWebResponse>.  
  
## <a name="examples"></a>Примеры  
 Дополнительные сведения см. в следующих разделах: [Практическое руководство. Скачивание файлов с использованием FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [Практическое руководство. Загрузка файлов с использованием FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) и [Практическое руководство. Список содержимого каталога с помощью FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).  
  
## <a name="ftp-and-proxies"></a>FTP и прокси-серверы  
 Если прокси-сервер, заданный свойством <xref:System.Net.FtpWebRequest.Proxy%2A>, является прокси-сервером HTTP, поддерживаются только команды <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> и <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.  
  
## <a name="see-also"></a>См. также  
 [Доступ к Интернету через прокси-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Пример клиентской технологии FTP](http://go.microsoft.com/fwlink/?LinkID=179557)  
 [Пример технологии FTP Explorer](http://go.microsoft.com/fwlink/?LinkID=179569)  
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)
