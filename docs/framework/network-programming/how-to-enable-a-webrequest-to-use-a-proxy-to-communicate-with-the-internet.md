---
title: Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 09a50794995b9157504ceff8dd578d709bfee020
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190447"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом
В этом примере создается экземпляр глобального прокси-сервера, который позволяет любому <xref:System.Net.WebRequest> использовать прокси-сервер для связи с Интернетом. В этом примере предполагается, что сервер имеет имя `webproxy` и подключается к стандартному HTTP-порту 80.  
  
## <a name="example"></a>Пример  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылки на пространство имен **System.Net**.  
  
## <a name="see-also"></a>См. также  
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)  
 [Доступ к Интернету через прокси-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
