---
title: Устранение рисков. Службы WCF и проверка подлинности сертификатов
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
ms.openlocfilehash: 8c8493efa2c3223809ad87e01e3faddaea859ca8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457791"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a>Устранение рисков. Службы WCF и проверка подлинности сертификатов

В платформе .NET Framework 4.6 в список протоколов WCF SSL по умолчанию добавляются протоколы TLS 1.1 и TLS 1.2. Если на клиентском компьютере и на сервере установлена платформа .NET Framework 4.6 или более поздняя версия, для согласования используется протокол TLS 1.2.

## <a name="impact"></a>Последствия

Протокол TLS 1.2 не поддерживает проверку подлинности MD5. В результате, если пользователь применяет SSL-сертификат, который использует хэш-алгоритм MD5, клиенту WCF не удается подключиться к службе WCF. Дополнительные сведения см. в разделе [Устранение рисков. Службы WCF и проверка подлинности сертификатов](mitigation-wcf-services-and-certificate-authentication.md).

## <a name="mitigation"></a>Меры по снижению риска

Эту проблему можно решить, чтобы клиент WCF мог подключиться к серверу WCF, выполнив любое из следующих действий.

- Обновите сертификат, чтобы он не использовал алгоритм MD5. Это рекомендуемое решение.

- Если привязка не настроена динамически в исходном коде, обновите файл конфигурации приложения, чтобы использовать TLS 1.1 или более раннюю версию протокола. Это позволяет продолжать использовать сертификат с хэш-алгоритмом MD5.

  > [!CAUTION]
  > Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.

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
      </system.serviceModel>
  </configuration>
  ```

- Если привязка настроена в исходном коде динамически, настройте свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> на использование TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) или более ранней версии протокола в исходном коде.

  > [!CAUTION]
  > Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.

## <a name="see-also"></a>См. также раздел

- [Совместимость приложений](application-compatibility.md)
