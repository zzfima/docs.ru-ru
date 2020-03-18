---
ms.openlocfilehash: b49b2f88b130bb952b77964d5bf38374dc606385
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567990"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a><span data-ttu-id="131f6-101">Для .NET Core 3.0 более предпочтительным является использование OpenSSL 1.1.x вместо OpenSSL 1.0.x</span><span class="sxs-lookup"><span data-stu-id="131f6-101">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>

<span data-ttu-id="131f6-102">.NET Core с поддержкой разных дистрибутивов Linux также поддерживает OpenSSL 1.0.x и OpenSSL 1.1.x.</span><span class="sxs-lookup"><span data-stu-id="131f6-102">.NET Core for Linux, which works across multiple Linux distributions, can support both OpenSSL 1.0.x and OpenSSL 1.1.x.</span></span>  <span data-ttu-id="131f6-103">.NET Core 2.1 и .NET Core 2.2 в первую очередь ищут версию 1.0.x и только потом версию 1.1.x; .NET Core 3.0 в первую очередь ищет версию 1.1.x.</span><span class="sxs-lookup"><span data-stu-id="131f6-103">.NET Core 2.1 and .NET Core 2.2 look for 1.0.x first, then fall back to 1.1.x; .NET Core 3.0 looks for 1.1.x first.</span></span> <span data-ttu-id="131f6-104">Это изменение было внесено, чтобы реализовать поддержку новых криптографических стандартов.</span><span class="sxs-lookup"><span data-stu-id="131f6-104">This change was made to add support for new cryptographic standards.</span></span>

<span data-ttu-id="131f6-105">Это изменение может повлиять на библиотеки или приложения, которые отвечают за взаимодействие между платформой и типами взаимодействия на основе OpenSSL в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="131f6-105">This change may impact libraries or applications that do platform interop with the OpenSSL-specific interop types in .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="131f6-106">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="131f6-106">Change description</span></span>

<span data-ttu-id="131f6-107">В .NET Core 2.2 и предыдущих версиях для среды выполнения предпочтительной является загрузка OpenSSL 1.0.x вместо 1.1.x.</span><span class="sxs-lookup"><span data-stu-id="131f6-107">In .NET Core 2.2 and earlier versions, the runtime prefers loading OpenSSL 1.0.x over 1.1.x.</span></span> <span data-ttu-id="131f6-108">Это означает, что типы <xref:System.IntPtr> и <xref:System.Runtime.InteropServices.SafeHandle> для взаимодействия с OpenSSL используются с libcrypto.so.1.0.0, libcrypto.so.1.0 или libcrypto.so.10 согласно предпочтениям.</span><span class="sxs-lookup"><span data-stu-id="131f6-108">This means that the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.0.0 / libcrypto.so.1.0 / libcrypto.so.10 by preference.</span></span>

<span data-ttu-id="131f6-109">Начиная с .NET Core 3.0, для среды выполнения предпочтительной является загрузка OpenSSL 1.1.x вместо OpenSSL 1.0.x, поэтому типы <xref:System.IntPtr> и <xref:System.Runtime.InteropServices.SafeHandle> для взаимодействия с OpenSSL используются с libcrypto.so.1.1, libcrypto.so.11, libcrypto.so.1.1.0 или libcrypto.so.1.1.1 согласно предпочтениям.</span><span class="sxs-lookup"><span data-stu-id="131f6-109">Starting with .NET Core 3.0, the runtime prefers loading OpenSSL 1.1.x over OpenSSL 1.0.x, so the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.1 / libcrypto.so.11 / libcrypto.so.1.1.0 / libcrypto.so.1.1.1 by preference.</span></span> <span data-ttu-id="131f6-110">В результате библиотеки и приложения, которые напрямую взаимодействуют с OpenSSL, могут иметь несовместимые указатели со значениями, предоставляемыми .NET Core, при обновлении с .NET Core 2.1 или .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="131f6-110">As a result, libraries and applications that interoperate with OpenSSL directly may have incompatible pointers with the .NET Core-exposed values when upgrading from .NET Core 2.1 or .NET Core 2.2.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="131f6-111">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="131f6-111">Version introduced</span></span>

<span data-ttu-id="131f6-112">3,0</span><span class="sxs-lookup"><span data-stu-id="131f6-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="131f6-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="131f6-113">Recommended action</span></span>

<span data-ttu-id="131f6-114">Библиотеки и приложения, которые выполняют прямые операции с OpenSSL, должны использовать ту же версию OpenSSL, которую использует среда выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="131f6-114">Libraries and applications that do direct operations with OpenSSL need to be careful to ensure they are using the same version of OpenSSL as the .NET Core runtime.</span></span>

<span data-ttu-id="131f6-115">Все библиотеки или приложения, использующие значения <xref:System.IntPtr> или <xref:System.Runtime.InteropServices.SafeHandle> криптографических типов .NET Core непосредственно с OpenSSL, должны сравнивать версию библиотеки, которую они используют, с новым свойством <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType>, чтобы обеспечить совместимость указателей.</span><span class="sxs-lookup"><span data-stu-id="131f6-115">All libraries or applications that use <xref:System.IntPtr> or <xref:System.Runtime.InteropServices.SafeHandle> values from the .NET Core cryptographic types directly with OpenSSL should compare the version of the library they use with the new <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property to ensure the pointers are compatible.</span></span>

#### <a name="category"></a><span data-ttu-id="131f6-116">Категория</span><span class="sxs-lookup"><span data-stu-id="131f6-116">Category</span></span>

<span data-ttu-id="131f6-117">Шифрование</span><span class="sxs-lookup"><span data-stu-id="131f6-117">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="131f6-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="131f6-118">Affected APIs</span></span>

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
