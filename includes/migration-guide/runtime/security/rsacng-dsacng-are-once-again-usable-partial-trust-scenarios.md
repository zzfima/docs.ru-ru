---
ms.openlocfilehash: 242a9952cb47d170aceffa1aa392071eb40cc6ab
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760694"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>RSACng и DSACng снова могут использоваться в сценариях частичного доверия

|   |   |
|---|---|
|Подробные сведения|CngLightup (используется в нескольких высокоуровневых API шифрования, таких как <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) и <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> в некоторых случаях требуют полного доверия. К ним относятся вызовы P/Invoke без утверждения разрешений <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>, а также пути кода, в которых <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> предъявляет требования к разрешениям для <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>. Начиная с версии .NET Framework 4.6.2, CngLightup по возможности используется для переключения на <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>. В результате приложения с частичным доверием, которые успешно использовали <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>, могут завершаться сбоем с исключениями <xref:System.Security.SecurityException>. Это изменение добавляет необходимые утверждения, благодаря чему все функции, использующие CngLightup, получают соответствующие разрешения.|
|Предложение|Если это изменение в .NET Framework 4.6.2 затронуло ваши приложения с частичным доверием, выполните обновление до версии .NET Framework 4.7.1.|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

