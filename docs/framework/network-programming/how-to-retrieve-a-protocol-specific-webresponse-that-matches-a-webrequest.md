---
title: Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: fee2b725afbceef45b9651a7cd88a61b37952e32
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087382"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="793f2-102">Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола</span><span class="sxs-lookup"><span data-stu-id="793f2-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="793f2-103">В этом примере показано, как получить объект WebResponse, соответствующий объекту WebRequest, для определенного протокола.</span><span class="sxs-lookup"><span data-stu-id="793f2-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="793f2-104">Пример</span><span class="sxs-lookup"><span data-stu-id="793f2-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="793f2-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="793f2-105">Compiling the Code</span></span>  
 <span data-ttu-id="793f2-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="793f2-106">This example requires:</span></span>  
  
-   <span data-ttu-id="793f2-107">Ссылки на пространство имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="793f2-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="793f2-108">См. также</span><span class="sxs-lookup"><span data-stu-id="793f2-108">See also</span></span>

- [<span data-ttu-id="793f2-109">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="793f2-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
