---
title: Практическое руководство. Переопределение глобальных прокси-серверов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2be271123e34f155a79269d3b810c50fe24a40c6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2018
ms.locfileid: "47235943"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="3e996-102">Практическое руководство. Переопределение глобальных прокси-серверов</span><span class="sxs-lookup"><span data-stu-id="3e996-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="3e996-103">В этом примере класс **WebRequest** отправляется на веб-сайт `www.contoso.com`, который переопределяет глобальные прокси-серверы прокси-сервером с именем `alternateproxy` на порту 80.</span><span class="sxs-lookup"><span data-stu-id="3e996-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e996-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3e996-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3e996-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3e996-105">Compiling the Code</span></span>  
 <span data-ttu-id="3e996-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="3e996-106">This example requires:</span></span>  
  
-   <span data-ttu-id="3e996-107">Директива [`using` ](~/docs/csharp/language-reference/keywords/using-directive.md) для пространства имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="3e996-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e996-108">См. также</span><span class="sxs-lookup"><span data-stu-id="3e996-108">See Also</span></span>  
 [<span data-ttu-id="3e996-109">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="3e996-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="3e996-110">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="3e996-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
