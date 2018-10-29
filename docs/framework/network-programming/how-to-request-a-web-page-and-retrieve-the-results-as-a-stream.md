---
title: Практическое руководство. Запрос веб-страницы и получение результатов в виде потока
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 6481e923c8daabfcfa94adc45d7d4172e47a779a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199075"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="9b1bc-102">Практическое руководство. Запрос веб-страницы и получение результатов в виде потока</span><span class="sxs-lookup"><span data-stu-id="9b1bc-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="9b1bc-103">В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.</span><span class="sxs-lookup"><span data-stu-id="9b1bc-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b1bc-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9b1bc-104">Example</span></span>  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b1bc-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9b1bc-105">Compiling the Code</span></span>  
 <span data-ttu-id="9b1bc-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="9b1bc-106">This example requires:</span></span>  
  
-   <span data-ttu-id="9b1bc-107">Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="9b1bc-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b1bc-108">См. также</span><span class="sxs-lookup"><span data-stu-id="9b1bc-108">See Also</span></span>  
 [<span data-ttu-id="9b1bc-109">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="9b1bc-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
