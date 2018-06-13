---
title: Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d15b63482cb37fa986dd065beefcf6baee4c8312
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394216"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a>Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола
В этом примере показано, как получить объект WebResponse, соответствующий объекту WebRequest, для определенного протокола.  
  
## <a name="example"></a>Пример  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылки на пространство имен **System.Net**.  
  
## <a name="see-also"></a>См. также  
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)
