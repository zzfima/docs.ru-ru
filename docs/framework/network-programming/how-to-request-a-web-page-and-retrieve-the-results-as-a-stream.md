---
title: Практическое руководство. Запрос веб-страницы и получение результатов в виде потока
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 65bda268cd77959dbcd786c365d0a30c324b89ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71393112"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="ba50b-102">Практическое руководство. Запрос веб-страницы и получение результатов в виде потока</span><span class="sxs-lookup"><span data-stu-id="ba50b-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="ba50b-103">В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.</span><span class="sxs-lookup"><span data-stu-id="ba50b-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="ba50b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ba50b-104">Example</span></span>

```csharp
var myClient = new WebClient();
Stream response = myClient.OpenRead("https://docs.microsoft.com/dotnet/");
// The stream data is used here.
response.Close();
```

```vb
Dim myClient As New WebClient()
Dim response As Stream = myClient.OpenRead("https://docs.microsoft.com/dotnet/")
' The stream data is used here.
response.Close()
```

## <a name="compiling-the-code"></a><span data-ttu-id="ba50b-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ba50b-105">Compiling the Code</span></span>

 <span data-ttu-id="ba50b-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ba50b-106">This example requires:</span></span>

- <span data-ttu-id="ba50b-107">Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="ba50b-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba50b-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ba50b-108">See also</span></span>

- [<span data-ttu-id="ba50b-109">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="ba50b-109">Requesting Data</span></span>](requesting-data.md)
