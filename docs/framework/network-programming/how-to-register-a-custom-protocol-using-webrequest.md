---
title: Как выполнить Регистрация пользовательского протокола с помощью WebRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 5c9a81fc61a2272056ba34fa387fdafee6203824
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079504"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a>Как выполнить Регистрация пользовательского протокола с помощью WebRequest
В этом примере показано, как зарегистрировать класс для конкретного протокола, который определен в другом месте. В этом примере `CustomWebRequestCreator` — пользовательский объект, который реализует метод **Create**, возвращающий объект `CustomWebRequest`. В примере кода предполагается, что вы написали код `CustomWebRequest`, который реализует пользовательский протокол.  
  
## <a name="example"></a>Пример  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
 Ссылки на пространство имен <xref:System.Net>.  
  
## <a name="see-also"></a>См. также

- [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
