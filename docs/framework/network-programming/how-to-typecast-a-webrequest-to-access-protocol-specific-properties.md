---
title: Практическое руководство. Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b4cde78ead9bdb8becf0f12497f4b37ad5a73bb3
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47421536"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="2fc79-102">Практическое руководство. Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом</span><span class="sxs-lookup"><span data-stu-id="2fc79-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="2fc79-103">В этом примере показано приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом.</span><span class="sxs-lookup"><span data-stu-id="2fc79-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fc79-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2fc79-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fc79-105">См. также</span><span class="sxs-lookup"><span data-stu-id="2fc79-105">See Also</span></span>  
 [<span data-ttu-id="2fc79-106">Программирование подключаемых протоколов</span><span class="sxs-lookup"><span data-stu-id="2fc79-106">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
