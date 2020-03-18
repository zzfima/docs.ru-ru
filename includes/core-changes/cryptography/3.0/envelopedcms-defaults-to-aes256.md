---
ms.openlocfilehash: f9000b19997201c2d3de0643669f9029ff1ca31c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567946"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a>Для EnvelopedCms по умолчанию используется шифрование AES-256

Алгоритм симметричного шифрования по умолчанию, используемый `EnvelopedCms`, изменен с TripleDES на AES-256.

#### <a name="change-description"></a>Описание изменений

Когда в предварительной версии .NET Core 7 и более ранних версиях использовался <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> для шифрования данных без указания алгоритма симметричного шифрования с помощью перегрузки конструктора, данные зашифровывались с помощью алгоритма TripleDES/3DES/3DEA/DES3-EDE.

Начиная с .NET Core 3.0 предварительной версии 8 (устанавливается с помощью пакета NuGet [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) версии 4.6.0), алгоритм по умолчанию был заменен на AES-256 с целью модернизации и повышения безопасности стандартных параметров. Если в сертификате получателя сообщения используется открытый ключ Диффи-Хеллмана (не EC) операция шифрования может завершиться ошибкой <xref:System.Security.Cryptography.CryptographicException> из-за ограничений базовой платформы.

В приведенном ниже примере кода показано, что в .NET Core 3.0 предварительной версии 7 или более ранней версии для шифрования данных используется TripleDES. При работе в .NET Core 3.0 предварительной версии 8 или более поздних версий для шифрование используется AES-256.

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a>Представленная версия

3.0 (предварительная версия 8)

#### <a name="recommended-action"></a>Рекомендованное действие

Если изменение отрицательно повлияет на работу, можете восстановить шифрование TripleDES, явно указав идентификатор алгоритма шифрования в конструкторе <xref:System.Security.Cryptography.Pkcs.EnvelopedCms>, который содержит параметр типа <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, например:

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a>Категория

Шифрование

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
