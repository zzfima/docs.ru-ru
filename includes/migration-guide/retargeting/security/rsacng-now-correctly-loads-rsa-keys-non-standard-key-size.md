---
ms.openlocfilehash: 4892f75e4ae673d9d9cc7e9eeb6fb9b1a73f572e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859262"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng теперь правильно загружает ключи RSA нестандартного размера

|   |   |
|---|---|
|Подробнее|В версиях .NET Framework до 4.6.2 клиенты с нестандартным размером ключа для сертификатов RSA не могли получить доступ к этим ключам через методы расширения <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> и <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name>.  Возникало исключение <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> с сообщением &quot;Запрошенный размер ключа не поддерживается&quot;. В .NET Framework 4.6.2 эта проблема была устранена. Аналогичным образом <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> и <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> теперь работают с нестандартными размерами ключа, не выдавая исключение <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>.|
|Предложение|Если существует логика обработки исключений, которая полагается на предыдущее поведение, когда при использовании ключей нестандартного размера возникало исключение <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, возможно, следует удалить эту логику.|
|Область|Пограничный случай|
|Version|4.6.2|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|
