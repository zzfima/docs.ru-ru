---
ms.openlocfilehash: b49b2f88b130bb952b77964d5bf38374dc606385
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567990"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a>Для .NET Core 3.0 более предпочтительным является использование OpenSSL 1.1.x вместо OpenSSL 1.0.x

.NET Core с поддержкой разных дистрибутивов Linux также поддерживает OpenSSL 1.0.x и OpenSSL 1.1.x.  .NET Core 2.1 и .NET Core 2.2 в первую очередь ищут версию 1.0.x и только потом версию 1.1.x; .NET Core 3.0 в первую очередь ищет версию 1.1.x. Это изменение было внесено, чтобы реализовать поддержку новых криптографических стандартов.

Это изменение может повлиять на библиотеки или приложения, которые отвечают за взаимодействие между платформой и типами взаимодействия на основе OpenSSL в .NET Core.

#### <a name="change-description"></a>Описание изменений

В .NET Core 2.2 и предыдущих версиях для среды выполнения предпочтительной является загрузка OpenSSL 1.0.x вместо 1.1.x. Это означает, что типы <xref:System.IntPtr> и <xref:System.Runtime.InteropServices.SafeHandle> для взаимодействия с OpenSSL используются с libcrypto.so.1.0.0, libcrypto.so.1.0 или libcrypto.so.10 согласно предпочтениям.

Начиная с .NET Core 3.0, для среды выполнения предпочтительной является загрузка OpenSSL 1.1.x вместо OpenSSL 1.0.x, поэтому типы <xref:System.IntPtr> и <xref:System.Runtime.InteropServices.SafeHandle> для взаимодействия с OpenSSL используются с libcrypto.so.1.1, libcrypto.so.11, libcrypto.so.1.1.0 или libcrypto.so.1.1.1 согласно предпочтениям. В результате библиотеки и приложения, которые напрямую взаимодействуют с OpenSSL, могут иметь несовместимые указатели со значениями, предоставляемыми .NET Core, при обновлении с .NET Core 2.1 или .NET Core 2.2.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

Библиотеки и приложения, которые выполняют прямые операции с OpenSSL, должны использовать ту же версию OpenSSL, которую использует среда выполнения .NET Core.

Все библиотеки или приложения, использующие значения <xref:System.IntPtr> или <xref:System.Runtime.InteropServices.SafeHandle> криптографических типов .NET Core непосредственно с OpenSSL, должны сравнивать версию библиотеки, которую они используют, с новым свойством <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>, чтобы обеспечить совместимость указателей.

#### <a name="category"></a>Категория

Шифрование

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.SafeEvpPKeyHandle.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Handle?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Security.Cryptography.SafeEvpPKeyHandle.#ctor`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.Security.CryptographySafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle`
- `P:System.Security.Cryptography.X509Certificates.X509Certificate.Handle`

-->
