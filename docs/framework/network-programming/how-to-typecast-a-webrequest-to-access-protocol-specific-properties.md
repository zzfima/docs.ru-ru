---
title: Практическое руководство. Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: a9488e484aad7ba3df23c33b2cb5b79f234b758e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088370"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a>Практическое руководство. Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом
В этом примере показано приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом.  
  
## <a name="example"></a>Пример  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a>См. также

- [программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
