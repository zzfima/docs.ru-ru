---
title: Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: d569603fe22e5d8c8f59d21c2777c7c1bfcd531d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048296"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="78dbf-102">Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом</span><span class="sxs-lookup"><span data-stu-id="78dbf-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="78dbf-103">В этом примере создается экземпляр глобального прокси-сервера, который позволяет любому <xref:System.Net.WebRequest> использовать прокси-сервер для связи с Интернетом.</span><span class="sxs-lookup"><span data-stu-id="78dbf-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="78dbf-104">В этом примере предполагается, что сервер имеет имя `webproxy` и подключается к стандартному HTTP-порту 80.</span><span class="sxs-lookup"><span data-stu-id="78dbf-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78dbf-105">Пример</span><span class="sxs-lookup"><span data-stu-id="78dbf-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="78dbf-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="78dbf-106">Compiling the Code</span></span>  
 <span data-ttu-id="78dbf-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="78dbf-107">This example requires:</span></span>  
  
- <span data-ttu-id="78dbf-108">Директива [`using` ](../../csharp/language-reference/keywords/using-directive.md) для пространства имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="78dbf-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78dbf-109">См. также</span><span class="sxs-lookup"><span data-stu-id="78dbf-109">See also</span></span>

- [<span data-ttu-id="78dbf-110">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="78dbf-110">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="78dbf-111">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="78dbf-111">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
