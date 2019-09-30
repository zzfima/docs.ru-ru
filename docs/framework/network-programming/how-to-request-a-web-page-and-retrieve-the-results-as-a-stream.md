---
title: Практическое руководство. Запрос веб-страницы и получение результатов в виде потока
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 65bda268cd77959dbcd786c365d0a30c324b89ce
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71393112"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="ff2c4-102">Практическое руководство. Запрос веб-страницы и получение результатов в виде потока</span><span class="sxs-lookup"><span data-stu-id="ff2c4-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="ff2c4-103">В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.</span><span class="sxs-lookup"><span data-stu-id="ff2c4-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="ff2c4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ff2c4-104">Example</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="ff2c4-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ff2c4-105">Compiling the Code</span></span>

 <span data-ttu-id="ff2c4-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ff2c4-106">This example requires:</span></span>

- <span data-ttu-id="ff2c4-107">Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="ff2c4-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff2c4-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ff2c4-108">See also</span></span>

- [<span data-ttu-id="ff2c4-109">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="ff2c4-109">Requesting Data</span></span>](requesting-data.md)
