---
title: "Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 937f4ac06ef4788c42b364fe03226e32a55572f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="1c0be-102">Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом</span><span class="sxs-lookup"><span data-stu-id="1c0be-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="1c0be-103">В этом примере создается экземпляр глобального прокси-сервера, который позволяет любому <xref:System.Net.WebRequest> использовать прокси-сервер для связи с Интернетом.</span><span class="sxs-lookup"><span data-stu-id="1c0be-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="1c0be-104">В этом примере предполагается, что сервер имеет имя `webproxy` и подключается к стандартному HTTP-порту 80.</span><span class="sxs-lookup"><span data-stu-id="1c0be-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c0be-105">Пример</span><span class="sxs-lookup"><span data-stu-id="1c0be-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1c0be-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1c0be-106">Compiling the Code</span></span>  
 <span data-ttu-id="1c0be-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="1c0be-107">This example requires:</span></span>  
  
-   <span data-ttu-id="1c0be-108">Ссылки на пространство имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="1c0be-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c0be-109">См. также</span><span class="sxs-lookup"><span data-stu-id="1c0be-109">See Also</span></span>  
 [<span data-ttu-id="1c0be-110">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="1c0be-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="1c0be-111">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="1c0be-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
