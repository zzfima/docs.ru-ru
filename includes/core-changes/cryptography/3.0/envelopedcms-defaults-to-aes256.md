---
ms.openlocfilehash: f9000b19997201c2d3de0643669f9029ff1ca31c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567946"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a><span data-ttu-id="e93a1-101">Для EnvelopedCms по умолчанию используется шифрование AES-256</span><span class="sxs-lookup"><span data-stu-id="e93a1-101">EnvelopedCms defaults to AES-256 encryption</span></span>

<span data-ttu-id="e93a1-102">Алгоритм симметричного шифрования по умолчанию, используемый `EnvelopedCms`, изменен с TripleDES на AES-256.</span><span class="sxs-lookup"><span data-stu-id="e93a1-102">The default symmetric encryption algorithm used by `EnvelopedCms` has changed from TripleDES to AES-256.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e93a1-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="e93a1-103">Change description</span></span>

<span data-ttu-id="e93a1-104">Когда в предварительной версии .NET Core 7 и более ранних версиях использовался <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> для шифрования данных без указания алгоритма симметричного шифрования с помощью перегрузки конструктора, данные зашифровывались с помощью алгоритма TripleDES/3DES/3DEA/DES3-EDE.</span><span class="sxs-lookup"><span data-stu-id="e93a1-104">In .NET Core Preview 7 and earlier versions, when <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> is used to encrypt data without specifying a symmetric encryption algorithm via a constructor overload, the data was encrypted with the TripleDES/3DES/3DEA/DES3-EDE algorithm.</span></span>

<span data-ttu-id="e93a1-105">Начиная с .NET Core 3.0 предварительной версии 8 (устанавливается с помощью пакета NuGet [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) версии 4.6.0), алгоритм по умолчанию был заменен на AES-256 с целью модернизации и повышения безопасности стандартных параметров.</span><span class="sxs-lookup"><span data-stu-id="e93a1-105">Starting with .NET Core 3.0 Preview 8 (via version 4.6.0 of the [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet package), the default algorithm has been changed to AES-256 for algorithm modernization and to improve the security of default options.</span></span> <span data-ttu-id="e93a1-106">Если в сертификате получателя сообщения используется открытый ключ Диффи-Хеллмана (не EC) операция шифрования может завершиться ошибкой <xref:System.Security.Cryptography.CryptographicException> из-за ограничений базовой платформы.</span><span class="sxs-lookup"><span data-stu-id="e93a1-106">If a message recipient certificate has a (non-EC) Diffie-Hellman public key, the encryption operation may fail with a <xref:System.Security.Cryptography.CryptographicException> due to limitations in the underlying platform.</span></span>

<span data-ttu-id="e93a1-107">В приведенном ниже примере кода показано, что в .NET Core 3.0 предварительной версии 7 или более ранней версии для шифрования данных используется TripleDES.</span><span class="sxs-lookup"><span data-stu-id="e93a1-107">In the following sample code, the data is encrypted with TripleDES if running on .NET Core 3.0 Preview 7 or earlier.</span></span> <span data-ttu-id="e93a1-108">При работе в .NET Core 3.0 предварительной версии 8 или более поздних версий для шифрование используется AES-256.</span><span class="sxs-lookup"><span data-stu-id="e93a1-108">If running on .NET Core 3.0 Preview 8 or later, it is encrypted with AES-256.</span></span>

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a><span data-ttu-id="e93a1-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="e93a1-109">Version introduced</span></span>

<span data-ttu-id="e93a1-110">3.0 (предварительная версия 8)</span><span class="sxs-lookup"><span data-stu-id="e93a1-110">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e93a1-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="e93a1-111">Recommended action</span></span>

<span data-ttu-id="e93a1-112">Если изменение отрицательно повлияет на работу, можете восстановить шифрование TripleDES, явно указав идентификатор алгоритма шифрования в конструкторе <xref:System.Security.Cryptography.Pkcs.EnvelopedCms>, который содержит параметр типа <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, например:</span><span class="sxs-lookup"><span data-stu-id="e93a1-112">If you are negatively impacted by the change, you can restore TripleDES encryption by explicitly specifying the encryption algorithm identifier in an <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> constructor that includes a parameter of type <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, such as:</span></span>

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a><span data-ttu-id="e93a1-113">Категория</span><span class="sxs-lookup"><span data-stu-id="e93a1-113">Category</span></span>

<span data-ttu-id="e93a1-114">Шифрование</span><span class="sxs-lookup"><span data-stu-id="e93a1-114">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e93a1-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e93a1-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
