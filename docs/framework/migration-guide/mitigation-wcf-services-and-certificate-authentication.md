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
ms.sourcegitcommit: 6f3dc4235c75d7438f019838cb22192f4dc7c41a
ms.openlocfilehash: 0b32fa96cd002e927fa00e8c2a797d1ff6b17cb8
ms.contentlocale: ru-ru
ms.lasthandoff: 05/30/2017

---
# Устранение рисков. Службы WCF и проверка подлинности сертификатов
<a id="mitigation-wcf-services-and-certificate-authentication" class="xliff"></a>
В платформе .NET Framework 4.6 в список протоколов WCF SSL по умолчанию добавляются протоколы TLS 1.1 и TLS 1.2. Если на клиентском компьютере и на сервере установлена платформа .NET Framework 4.6 или более поздняя версия, для согласования используется протокол TLS 1.2.  
  
## Последствия
<a id="impact" class="xliff"></a>  
 Протокол TLS 1.2 не поддерживает проверку подлинности MD5. В результате, если пользователь применяет SSL-сертификат, который использует хэш-алгоритм MD5, клиенту WCF не удается подключиться к службе WCF. Дополнительные сведения см. в разделе [Устранение рисков. Службы WCF и проверка подлинности сертификатов](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).  
  
## Уменьшение
<a id="mitigation" class="xliff"></a>  
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
  
-   Если привязка настроена в исходном коде динамически, настройте свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName> на использование TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=fullName>) или более ранней версии протокола в исходном коде.  
  
    > [!CAUTION]
    >  Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.  
  
## См. также
<a id="see-also" class="xliff"></a>  
 [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)

