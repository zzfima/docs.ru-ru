---
title: FTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d7b169a6de494d10fa332ebf5f2aa315ae69653a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ftp"></a><span data-ttu-id="1819a-102">FTP</span><span class="sxs-lookup"><span data-stu-id="1819a-102">FTP</span></span>
<span data-ttu-id="1819a-103">Платформа .NET Framework обеспечивает полную поддержку протокола FTP посредством классов <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="1819a-103">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="1819a-104">Эти классы являются производными от <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="1819a-104">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="1819a-105">В большинстве случаев классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> предоставляют все необходимое для выполнения запроса, но если вам требуется доступ к возможностям протокола FTP, представленным в виде свойств, можно выполнить приведение типа этих классов к <xref:System.Net.FtpWebRequest> или <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="1819a-105">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1819a-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="1819a-106">Examples</span></span>  
 <span data-ttu-id="1819a-107">Дополнительные сведения см. в следующих разделах: [Практическое руководство. Скачивание файлов с использованием FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [Практическое руководство. Загрузка файлов с использованием FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) и [Практическое руководство. Список содержимого каталога с помощью FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="1819a-107">For more information, see the following topics: [How to: Download Files with FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span></span>  
  
## <a name="ftp-and-proxies"></a><span data-ttu-id="1819a-108">FTP и прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="1819a-108">FTP and proxies</span></span>  
 <span data-ttu-id="1819a-109">Если прокси-сервер, заданный свойством <xref:System.Net.FtpWebRequest.Proxy%2A>, является прокси-сервером HTTP, поддерживаются только команды <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> и <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.</span><span class="sxs-lookup"><span data-stu-id="1819a-109">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1819a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1819a-110">See Also</span></span>  
 [<span data-ttu-id="1819a-111">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="1819a-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="1819a-112">Примеры сетевого программирования</span><span class="sxs-lookup"><span data-stu-id="1819a-112">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="1819a-113">Пример клиентской технологии FTP</span><span class="sxs-lookup"><span data-stu-id="1819a-113">FTP Client Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179557)  
 [<span data-ttu-id="1819a-114">Пример технологии FTP Explorer</span><span class="sxs-lookup"><span data-stu-id="1819a-114">FTP Explorer Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179569)  
 [<span data-ttu-id="1819a-115">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="1819a-115">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
