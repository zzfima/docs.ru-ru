---
title: Практическое руководство. Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: a224d9dbab0157d77c05a5937fe35c027296a674
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048023"
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

- [Программирование подключаемых протоколов](programming-pluggable-protocols.md)
