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
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>Как выполнить Запрос веб-страницы и получение результатов в виде потока
В этом примере показано, как запросить веб-страницу и получить результаты в виде потока.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылки на пространства имен <xref:System.IO> и <xref:System.Net>.  
  
## <a name="see-also"></a>См. также
- [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)
