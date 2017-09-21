---
title: "Практическое руководство. Переопределение глобальных прокси-серверов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
caps.latest.revision: 8
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cecb98628231e6a8b2847043e3f3c2206c164ae3
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-override-a-global-proxy-selection"></a>Практическое руководство. Переопределение глобальных прокси-серверов
В этом примере класс **WebRequest** отправляется на веб-сайт www.contoso.com, который переопределяет глобальные прокси-серверы прокси-сервером с именем `alternateproxy` на порту 80.  
  
## <a name="example"></a>Пример  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылки на пространство имен **System.Net**.  
  
## <a name="see-also"></a>См. также  
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Доступ к Интернету через прокси-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)

