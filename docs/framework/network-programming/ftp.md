---
title: FTP — .NET
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d945f03077a863d9e1baa6b59fe8a908566aba5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "61642884"
---
# <a name="ftp"></a>FTP

Платформа .NET Framework обеспечивает полную поддержку протокола FTP посредством классов <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse>. Эти классы являются производными от <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>. В большинстве случаев классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> предоставляют все необходимое для выполнения запроса, но если вам требуется доступ к возможностям протокола FTP, представленным в виде свойств, можно выполнить приведение типа этих классов к <xref:System.Net.FtpWebRequest> или <xref:System.Net.FtpWebResponse>.

## <a name="examples"></a>Примеры

Дополнительные сведения см. в следующих разделах: [Практическое руководство. Скачивание файлов с использованием FTP](how-to-download-files-with-ftp.md), [Практическое руководство. Загрузка файлов с использованием FTP](how-to-upload-files-with-ftp.md) и [Практическое руководство. Список содержимого каталога с помощью FTP](how-to-list-directory-contents-with-ftp.md).

## <a name="ftp-and-proxies"></a>FTP и прокси-серверы

Если прокси-сервер, заданный свойством <xref:System.Net.FtpWebRequest.Proxy%2A>, является прокси-сервером HTTP, поддерживаются только команды <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> и <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.

## <a name="see-also"></a>См. также раздел

- [Доступ к Интернету через прокси-сервер](accessing-the-internet-through-a-proxy.md)
- [Примеры сетевого программирования](network-programming-samples.md)
- [Использование протоколов приложений](using-application-protocols.md)
