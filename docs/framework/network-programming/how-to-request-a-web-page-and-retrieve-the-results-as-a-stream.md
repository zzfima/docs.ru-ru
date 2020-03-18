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
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>Практическое руководство. Запрос веб-страницы и получение результатов в виде потока

В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.
  
## <a name="example"></a>Пример

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

## <a name="compiling-the-code"></a>Компиляция кода

 Для этого примера требуются:

- Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.

## <a name="see-also"></a>См. также раздел

- [Запрос данных](requesting-data.md)
