---
title: Как выполнить Запрос веб-страницы и получение результатов в виде потока
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 5ef1867d84b619c58a7b3e29ed0f81f9db0c07a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578589"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="b0806-102">Как выполнить Запрос веб-страницы и получение результатов в виде потока</span><span class="sxs-lookup"><span data-stu-id="b0806-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="b0806-103">В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.</span><span class="sxs-lookup"><span data-stu-id="b0806-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0806-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b0806-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="b0806-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b0806-105">Compiling the Code</span></span>  
 <span data-ttu-id="b0806-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b0806-106">This example requires:</span></span>  
  
-   <span data-ttu-id="b0806-107">Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="b0806-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0806-108">См. также</span><span class="sxs-lookup"><span data-stu-id="b0806-108">See also</span></span>
- [<span data-ttu-id="b0806-109">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="b0806-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
