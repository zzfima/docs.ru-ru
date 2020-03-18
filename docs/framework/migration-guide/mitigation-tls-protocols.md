---
title: Устранение рисков. Протоколы TLS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: 45225d73ac60564d3e22c73270faab6b4e04d697
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457834"
---
# <a name="mitigation-tls-protocols"></a>Устранение рисков. Протоколы TLS
Начиная с версии .NET Framework 4.6, классы <xref:System.Net.ServicePointManager?displayProperty=nameWithType> и <xref:System.Net.Security.SslStream?displayProperty=nameWithType> могут использовать один из трех следующих протоколов: Tls1.0, Tls1.1 или Tls 1.2. Протокол SSL 3.0 и шифрование RC4 не поддерживаются.  
  
## <a name="impact"></a>Последствия  
 Это изменение влияет:  
  
- на все приложения, использующие протокол SSL для связи с сервером HTTPS или сервером сокетов с помощью любого из следующих типов: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> и <xref:System.Net.Security.SslStream>;  
  
- на все приложения на стороне сервера, которые нельзя обновить для поддержки Tls1.0, Tls1.1 или Tls 1.2.  
  
## <a name="mitigation"></a>Меры по снижению риска  
 Рекомендуется обновить приложения на стороне сервера для использования Tls1.0, Tls1.1 или Tls 1.2. Если это невозможно, или если клиентские приложения не работают, можно использовать класс <xref:System.AppContext>, чтобы отказаться от этой функции одним из двух способов.  
  
- Программно с помощью фрагмента кода следующего вида:  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     Поскольку объект <xref:System.Net.ServicePointManager> инициализируется только один раз, определение этих параметров совместимости должно быть первым действием приложения.  
  
- Путем добавления следующей строки в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла app.config:  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 Следует, тем не менее, заметить, что отказ от поведения по умолчанию не рекомендуется, поскольку приводит к снижению безопасности приложения.  
  
## <a name="see-also"></a>См. также раздел

- [Совместимость приложений](application-compatibility.md)
