---
title: Практическое руководство. Запрос веб-страницы и получение результатов в виде потока
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: b3d24a958ec93084d03d2ad2e0eb6d9d2507e155
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048177"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="086c9-102">Практическое руководство. Запрос веб-страницы и получение результатов в виде потока</span><span class="sxs-lookup"><span data-stu-id="086c9-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="086c9-103">В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.</span><span class="sxs-lookup"><span data-stu-id="086c9-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="086c9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="086c9-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="086c9-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="086c9-105">Compiling the Code</span></span>  
 <span data-ttu-id="086c9-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="086c9-106">This example requires:</span></span>  
  
- <span data-ttu-id="086c9-107">Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="086c9-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086c9-108">См. также</span><span class="sxs-lookup"><span data-stu-id="086c9-108">See also</span></span>

- [<span data-ttu-id="086c9-109">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="086c9-109">Requesting Data</span></span>](requesting-data.md)
