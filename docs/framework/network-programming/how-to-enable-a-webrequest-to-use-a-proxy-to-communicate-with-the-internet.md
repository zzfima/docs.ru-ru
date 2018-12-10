---
title: Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 1b10d895478a88556cf1d716480de568c8e9c9ad
ms.sourcegitcommit: 2151690e10d91545e2c20d6b5ad222c162b6b83d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2018
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
  
-   Директива [`using` ](../../csharp/language-reference/keywords/using-directive.md) для пространства имен **System.Net**.  
  
## <a name="see-also"></a>См. также  
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)  
 [Доступ к Интернету через прокси-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
