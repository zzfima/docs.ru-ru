---
title: Практическое руководство. Регистрация пользовательского протокола с помощью WebRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1f78f98f94daa51c17a1294285e13dfddd457106
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47230973"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="116f0-102">Практическое руководство. Регистрация пользовательского протокола с помощью WebRequest</span><span class="sxs-lookup"><span data-stu-id="116f0-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="116f0-103">В этом примере показано, как зарегистрировать класс для конкретного протокола, который определен в другом месте.</span><span class="sxs-lookup"><span data-stu-id="116f0-103">This example shows how to register a protocol specific classthat is defined elsewhere.</span></span> <span data-ttu-id="116f0-104">В этом примере `CustomWebRequestCreator` — пользовательский объект, который реализует метод **Create**, возвращающий объект `CustomWebRequest`.</span><span class="sxs-lookup"><span data-stu-id="116f0-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="116f0-105">В примере кода предполагается, что вы написали код `CustomWebRequest`, который реализует пользовательский протокол.</span><span class="sxs-lookup"><span data-stu-id="116f0-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="116f0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="116f0-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="116f0-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="116f0-107">Compiling the Code</span></span>  
 <span data-ttu-id="116f0-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="116f0-108">This example requires:</span></span>  
  
 <span data-ttu-id="116f0-109">Ссылки на пространство имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="116f0-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="116f0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="116f0-110">See Also</span></span>  
 [<span data-ttu-id="116f0-111">Программирование подключаемых протоколов</span><span class="sxs-lookup"><span data-stu-id="116f0-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
