---
ms.openlocfilehash: 9e8fdb54bddc32c08adbe114e2d46e2508585bc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858505"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a>Службы WCF, использующие NETTCP с уровнем безопасности SSL и проверкой подлинности на основе сертификатов MD5

|   |   |
|---|---|
|Подробнее|В платформе .NET Framework 4.6 в список протоколов WCF SSL по умолчанию добавляются протоколы TLS 1.1 и TLS 1.2. Если на клиентском компьютере и на сервере установлена платформа .NET Framework 4.6 или более поздняя версия, для согласования используется протокол TLS 1.2. Протокол TLS 1.2 не поддерживает проверку подлинности на основе сертификатов MD5. Поэтому, если используется сертификат MD5, клиент WCF не сможет подключиться к службе WCF.|
|Предложение|Эту проблему можно решить, чтобы клиент WCF мог подключиться к серверу WCF, выполнив любое из следующих действий.<ul><li>Обновите сертификат, чтобы он не использовал алгоритм MD5. Это рекомендуемое решение.</li><li>Если привязка не настроена динамически в исходном коде, обновите файл конфигурации приложения, чтобы использовать TLS 1.1 или более раннюю версию протокола. Это позволяет продолжать использовать сертификат с хэш-алгоритмом MD5.</li></ul> <blockquote> [!WARNING] Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.</blockquote> Это выполняется в следующем файле конфигурации:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.serviceModel&gt;&#13;&#10;&lt;bindings&gt;&#13;&#10;&lt;netTcpBinding&gt;&#13;&#10;&lt;binding&gt;&#13;&#10;&lt;security mode= &quot;None/Transport/Message/TransportWithMessageCredential&quot; &gt;&#13;&#10;&lt;transport clientCredentialType=&quot;None/Windows/Certificate&quot;&#13;&#10;protectionLevel=&quot;None/Sign/EncryptAndSign&quot;&#13;&#10;sslProtocols=&quot;Ssl3/Tls1/Tls11&quot;&gt;&#13;&#10;&lt;/transport&gt;&#13;&#10;&lt;/security&gt;&#13;&#10;&lt;/binding&gt;&#13;&#10;&lt;/netTcpBinding&gt;&#13;&#10;&lt;/bindings&gt;&#13;&#10;&lt;/system.ServiceModel&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><ul><li>Если привязка настроена в исходном коде динамически, настройте свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> на использование TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) или более ранней версии протокола в исходном коде.</li></ul> <blockquote> [!WARNING] Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.</blockquote> |
|Область|Дополнительный номер|
|Version|4.6|
|Type|Параметры выполнения|
