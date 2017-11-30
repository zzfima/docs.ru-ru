---
title: HTTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 701ff252380ef93dbe3668c8aca73f08a8425d6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="http"></a><span data-ttu-id="dcaf0-102">HTTP</span><span class="sxs-lookup"><span data-stu-id="dcaf0-102">HTTP</span></span>
<span data-ttu-id="dcaf0-103">Платформа .NET предоставляет полную поддержку для протокола HTTP, который приходится большая часть все Интернет-трафик с <xref:System.Net.HttpWebRequest> и <xref:System.Net.HttpWebResponse> классы.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-103">The .NET Framework provides comprehensive support for the HTTP protocol, which makes up the majority of all Internet traffic, with the <xref:System.Net.HttpWebRequest> and <xref:System.Net.HttpWebResponse> classes.</span></span> <span data-ttu-id="dcaf0-104">Эти классы, производные от <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, возвращаются по умолчанию всякий раз, когда статический метод <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> обнаруживает URI, начинающийся с "http" или "https".</span><span class="sxs-lookup"><span data-stu-id="dcaf0-104">These classes, derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, are returned by default whenever the static method <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> encounters a URI beginning with "http" or "https".</span></span> <span data-ttu-id="dcaf0-105">В большинстве случаев классы **WebRequest** и **WebResponse** предоставляют все необходимое для выполнения запроса, но если вам необходим доступ к возможностям HTTP-протокола, представленным в виде свойств, можно выполнить приведение этих классов к **HttpWebRequest** или **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-105">In most cases, the **WebRequest** and **WebResponse** classes provide all that is necessary to make the request, but if you need access to the HTTP-specific features exposed as properties, you can typecast these classes to **HttpWebRequest** or **HttpWebResponse**.</span></span>  
  
 <span data-ttu-id="dcaf0-106">Классы **HttpWebRequest** и **HttpWebResponse** инкапсулируют стандартную транзакцию "запрос-ответ" HTTP и предоставляют доступ к основным заголовкам HTTP.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-106">**HttpWebRequest** and **HttpWebResponse** encapsulate a standard HTTP request-and-response transaction and provide access to common HTTP headers.</span></span> <span data-ttu-id="dcaf0-107">Эти классы также поддерживают большинство функций HTTP 1.1, включая конвейеризацию, отправку и получение данных в блоках, проверку подлинности, предварительную проверку подлинности, шифрование, поддержку прокси-сервера, проверку сертификата сервера и управление соединениями.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-107">These classes also support most HTTP 1.1 features, including pipelining, sending and receiving data in chunks, authentication, preauthentication, encryption, proxy support, server certificate validation, and connection management.</span></span> <span data-ttu-id="dcaf0-108">Пользовательские заголовки и заголовки, доступ к которым через свойства не предоставляется, можно получить в разделе **Заголовки**.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-108">Custom headers and headers not provided through properties can be stored in and accessed through the **Headers** property.</span></span>  
  
 <span data-ttu-id="dcaf0-109">Класс **HttpWebRequest** — класс по умолчанию, который используется классом **WebRequest**. Этот класс не требуется регистрировать перед тем, как передавать URI в метод **WebRequest.Create**.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-109">**HttpWebRequest** is the default class used by **WebRequest** and does not need to be registered before you can pass a URI to the **WebRequest.Create** method.</span></span>  
  
 <span data-ttu-id="dcaf0-110">Чтобы приложение автоматически перенаправляло запросы HTTP, можно установить свойство <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> в значение **true** (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="dcaf0-110">You can make your application follow HTTP redirects automatically by setting the <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> property to **true** (the default).</span></span> <span data-ttu-id="dcaf0-111">Приложение будет перенаправлять запросы, а свойство <xref:System.Net.HttpWebResponse.ResponseUri%2A> объекта **HttpWebResponse** будет содержать веб-ресурс, который ответил на запрос.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-111">The application will redirect requests, and the <xref:System.Net.HttpWebResponse.ResponseUri%2A> property of **HttpWebResponse** will contain the actual Web resource that responded to the request.</span></span> <span data-ttu-id="dcaf0-112">Если установить свойство **AllowAutoRedirect** в значение **false**, приложение сможет обрабатывать перенаправления как ошибки протокола HTTP.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-112">If you set **AllowAutoRedirect** to **false**, your application must be able to handle redirects as HTTP protocol errors.</span></span>  
  
 <span data-ttu-id="dcaf0-113">Приложения получают ошибки протокола HTTP, перехватывая <xref:System.Net.WebException> со свойством <xref:System.Net.WebException.Status%2A>, установленным в значение <xref:System.Net.WebExceptionStatus>.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-113">Applications receive HTTP protocol errors by catching a <xref:System.Net.WebException> with the <xref:System.Net.WebException.Status%2A> set to <xref:System.Net.WebExceptionStatus>.</span></span> <span data-ttu-id="dcaf0-114">Свойство <xref:System.Net.WebException.Response%2A> означает фактическую обнаруженную ошибку HTTP и содержит объект **WebResponse**, отправленный сервером.</span><span class="sxs-lookup"><span data-stu-id="dcaf0-114">The <xref:System.Net.WebException.Response%2A> property contains the **WebResponse** sent by the server and indicates the actual HTTP error encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcaf0-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dcaf0-115">See Also</span></span>  
 [<span data-ttu-id="dcaf0-116">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="dcaf0-116">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="dcaf0-117">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="dcaf0-117">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="dcaf0-118">Практическое руководство. Доступ к свойствам, относящимся с HTTP</span><span class="sxs-lookup"><span data-stu-id="dcaf0-118">How to: Access HTTP-Specific Properties</span></span>](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)
