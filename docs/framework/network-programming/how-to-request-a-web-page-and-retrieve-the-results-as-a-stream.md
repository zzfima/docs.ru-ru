---
title: Как выполнить Запрос веб-страницы и получение результатов в виде потока
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 23c094f0a3f528750c9589dbc99a0ada86236967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097204"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="90e83-102">Как выполнить Запрос веб-страницы и получение результатов в виде потока</span><span class="sxs-lookup"><span data-stu-id="90e83-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="90e83-103">В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.</span><span class="sxs-lookup"><span data-stu-id="90e83-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90e83-104">Пример</span><span class="sxs-lookup"><span data-stu-id="90e83-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="90e83-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="90e83-105">Compiling the Code</span></span>  
 <span data-ttu-id="90e83-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="90e83-106">This example requires:</span></span>  
  
-   <span data-ttu-id="90e83-107">Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="90e83-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e83-108">См. также</span><span class="sxs-lookup"><span data-stu-id="90e83-108">See also</span></span>

- [<span data-ttu-id="90e83-109">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="90e83-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
