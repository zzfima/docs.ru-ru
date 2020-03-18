---
ms.openlocfilehash: cdcf7f540a9ded4108121b2cd8e855687a0c7e27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858925"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a>SignedXml.GetPublicKey возвращает RSACng в net462 (или lightup) без изменения целевой платформы

|   |   |
|---|---|
|Подробнее|Начиная с .NET Framework 4.6.2 конкретный тип объекта, возвращаемого методом <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType>, изменен (без особенностей) с реализации CryptoServiceProvider на реализацию Cng. Это связано с изменениями реализации, предусматривающими использование <code>certificate.PublicKey.Key</code> вместо внутреннего <code>certificate.GetAnyPublicKey</code> с переадресацией к <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.|
|Предложение|Начиная с приложений, выполняющихся в .NET Framework 4.7.1, вы можете использовать реализацию CryptoServiceProvider, используемую по умолчанию на платформе .NET Framework 4.6.1 и более ранних версий, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true&quot; /&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Version|4.6.2|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType></li></ul>|
