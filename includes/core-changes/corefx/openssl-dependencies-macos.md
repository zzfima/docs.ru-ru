---
ms.openlocfilehash: 6a5cd260a2820e2a81142f6d55e32e91173ca503
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147455"
---
### <a name="openssl-versions-on-macos"></a>Версии OpenSSL в macOS

В среде выполнения .NET Core 3.0 и более поздних версий в macOS вместо версий OpenSSL 1.0.x для типов <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> и <xref:System.Security.Cryptography.SafeEvpPKeyHandle> теперь предпочтительно использовать версии OpenSSL 1.1.x.

Среда выполнения .NET Core 2.1 теперь поддерживает версии OpenSSL 1.1.x, однако предпочтительными по-прежнему являются версии OpenSSL 1.0.x.

#### <a name="change-description"></a>Описание изменений

Ранее в среде выполнения .NET Core для типов, которые взаимодействуют с OpenSSL, использовались версии OpenSSL 1.0.x в macOS. Последняя версия OpenSSL 1.0.x (OpenSSL 1.0.2) теперь не поддерживается. Для сохранения типов, использующих OpenSSL в поддерживаемых версиях OpenSSL, в средах выполнения .NET Core 3.0 и более поздних версий теперь используются более новые версии OpenSSL в macOS.

В связи с этим изменением поведение сред выполнения .NET Core в macOS теперь реализуется следующим образом.

- В средах выполнения .NET Core 3.0 и более поздних версий при условии доступности используется OpenSSL 1.1.x, и только если версия 1.1.x не доступна, осуществляется откат к OpenSSL 1.0.x.

  Для вызывающих объектов, использующих типы взаимодействия OpenSSL с пользовательскими методами P/Invoke, необходимо следовать указаниям в примечаниях <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>. Если не проверить значение <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion>, приложение может аварийно завершить работу.

- В средах выполнения .NET Core 2.1 при условии доступности используется OpenSSL 1.0.x, а если версия 1.0.x не доступна, осуществляется откат к OpenSSL 1.1.x.

  В среде выполнения версии 2.1 предпочтительно использовать более раннюю версию OpenSSL, поскольку в .NET Core 2.1 отсутствует свойство <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>, в связи с чем во время выполнения невозможно гарантированно определить версию OpenSSL.

#### <a name="version-introduced"></a>Представленная версия

- .NET Core 2.1.16
- .NET Core 3.0.3
- .NET Core 3.1.2

#### <a name="recommended-action"></a>Рекомендованное действие

- Удалите версию OpenSSL 1.0.2, если она больше не требуется.

- Установите версию OpenSSL 1.1.x, если используются типы <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> или <xref:System.Security.Cryptography.SafeEvpPKeyHandle>.

- Если вы используете типы взаимодействия OpenSSL с пользовательскими методами P/Invoke, необходимо следовать указаниям в примечаниях <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->
