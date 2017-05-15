---
title: "Устранение рисков. Службы WCF и проверка подлинности сертификатов | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4c2156087ca168bafb1b7333310066cef73f3334
ms.contentlocale: ru-ru
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a>Устранение рисков. Службы WCF и проверка подлинности сертификатов
В платформе .NET Framework 4.6 в список протоколов WCF SSL по умолчанию добавляются протоколы TLS 1.1 и TLS 1.2. Если на клиентском компьютере и на сервере установлена платформа .NET Framework 4.6 или более поздняя версия, для согласования используется протокол TLS 1.2.  
  
## <a name="impact"></a>Последствия  
 Протокол TLS 1.2 не поддерживает проверку подлинности MD5. В результате, если пользователь применяет SSL-сертификат, который использует хэш-алгоритм MD5, клиенту WCF не удается подключиться к службе WCF. Дополнительные сведения см. в разделе [Устранение рисков. Службы WCF и проверка подлинности сертификатов](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).  
  
## <a name="mitigation"></a>Уменьшение  
 Эту проблему можно решить, чтобы клиент WCF мог подключиться к серверу WCF, выполнив любое из следующих действий.  
  
-   Обновите сертификат, чтобы он не использовал алгоритм MD5. Это рекомендуемое решение.  
  
-   Если привязка не настроена динамически в исходном коде, обновите файл конфигурации приложения, чтобы использовать TLS 1.1 или более раннюю версию протокола. Это позволяет продолжать использовать сертификат с хэш-алгоритмом MD5.  
  
    > [!CAUTION]
    >  Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.  
  
     Это выполняется в следующем файле конфигурации:  
  
    ```xml  
  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding>  
                        <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                            <transport clientCredentialType="None|Windows|Certificate"  
                                                protectionLevel="None|Sign|EncryptAndSign"  
                                                sslProtocols="Ssl3|Tls1|Tls11">  
                            </transport>  
                        </security>  
                    </binding>  
                </netTcpBinding>  
            </bindings>  
        </system.ServiceModel>  
    </configuration>  
  
    ```  
  
-   Если привязка динамически настраивается в исходном коде, обновите свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName> для использования TLS 1.1 (<xref:System.Security.Authentication.SslProtocols?displayProperty=fullName>) или более ранней версии протокола в исходном коде.  
  
    > [!CAUTION]
    >  Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.  
  
## <a name="see-also"></a>См. также  
 [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)

