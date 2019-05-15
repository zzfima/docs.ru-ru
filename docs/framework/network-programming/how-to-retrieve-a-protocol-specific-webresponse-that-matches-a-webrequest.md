---
title: Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 21a5a81c6a5457897078db03fe35eaff330ed62d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647372"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="31450-102">Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола</span><span class="sxs-lookup"><span data-stu-id="31450-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="31450-103">В этом примере показано, как получить объект WebResponse, соответствующий объекту WebRequest, для определенного протокола.</span><span class="sxs-lookup"><span data-stu-id="31450-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31450-104">Пример</span><span class="sxs-lookup"><span data-stu-id="31450-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31450-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="31450-105">Compiling the Code</span></span>  
 <span data-ttu-id="31450-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="31450-106">This example requires:</span></span>  
  
- <span data-ttu-id="31450-107">Ссылки на пространство имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="31450-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31450-108">См. также</span><span class="sxs-lookup"><span data-stu-id="31450-108">See also</span></span>

- [<span data-ttu-id="31450-109">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="31450-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
