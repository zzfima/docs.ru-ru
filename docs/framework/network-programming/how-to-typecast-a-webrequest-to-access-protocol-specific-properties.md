---
title: Как выполнить Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: 6202b0b02d334c076dbe41a785195344dd2d7efe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564517"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a>Как выполнить Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом
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
- [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
