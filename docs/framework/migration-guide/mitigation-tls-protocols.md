---
title: "Устранение рисков. Протоколы TLS | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1474aeb0e1be38018f9d27c49e8711800ecb9f01
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-tls-protocols"></a>Устранение рисков. Протоколы TLS
Начиная с .NET Framework 4.6 классы <xref:System.Net.ServicePointManager?displayProperty=fullName> и <xref:System.Net.Security.SslStream?displayProperty=fullName> могут использовать один из трех следующих протоколов: Tls1.0, Tls1.1 или Tls 1.2. Протокол SSL 3.0 и шифрование RC4 не поддерживаются.  
  
## <a name="impact"></a>Последствия  
 Это изменение влияет:  
  
-   на все приложения, использующие SSL для связи с HTTPS-сервером или сервером сокетов с применением любого из следующих типов: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> и <xref:System.Net.Security.SslStream>;  
  
-   на все приложения на стороне сервера, которые нельзя обновить для поддержки Tls1.0, Tls1.1 или Tls 1.2.  
  
## <a name="mitigation"></a>Уменьшение  
 Рекомендуется обновить приложения на стороне сервера для использования Tls1.0, Tls1.1 или Tls 1.2. Если это невозможно или если клиентские приложения не работают, можно использовать класс <xref:System.AppContext>, чтобы отказаться от этой возможности одним из двух способов.  
  
-   Программно с помощью фрагмента кода следующего вида:  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     Поскольку объект <xref:System.Net.ServicePointManager> инициализируется только один раз, определение этих параметров совместимости должно быть первым действием приложения.  
  
-   Путем добавления следующей строки в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 Следует, тем не менее, заметить, что отказ от поведения по умолчанию не рекомендуется, поскольку приводит к снижению безопасности приложения.  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
