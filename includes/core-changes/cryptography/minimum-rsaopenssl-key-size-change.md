---
ms.openlocfilehash: 07ab65de16b72bd0844a39e4b35235c5f043f3ec
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117178"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a><span data-ttu-id="2162a-101">Увеличен минимальный размер создаваемых ключей RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="2162a-101">Minimum size for RSAOpenSsl key generation has increased</span></span>

<span data-ttu-id="2162a-102">Минимальный размер создаваемых ключей RSA в Linux увеличен с 384 до 512 бит.</span><span class="sxs-lookup"><span data-stu-id="2162a-102">The minimum size for generating new RSA keys on Linux has increased from 384-bit to 512-bit.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2162a-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="2162a-103">Change description</span></span>

<span data-ttu-id="2162a-104">Начиная с .NET Core 3.0, минимальный допустимый размер ключа, передаваемый свойством `LegalKeySizes` в экземплярах RSA из <System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType> и <System.Security.Cryptography.RSACryptoServicePlatform.%23ctor%2A?displayProperty=nameWithType> в Linux, увеличен с 384 до 512 бит.</span><span class="sxs-lookup"><span data-stu-id="2162a-104">Starting with .NET Core 3.0, the minimum legal key size reported by the `LegalKeySizes` property on RSA instances from <System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>, and <System.Security.Cryptography.RSACryptoServicePlatform.%23ctor%2A?displayProperty=nameWithType> on Linux has increased from 384 to 512.</span></span>

<span data-ttu-id="2162a-105">В результате в .NET Core 2.2 и более ранних версий вызов такого метода, как `RSA.Create(384)`, выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="2162a-105">As a result, in .NET Core 2.2 and earlier versions, a method call such as `RSA.Create(384)` succeeds.</span></span> <span data-ttu-id="2162a-106">В .NET Core 3.0 и более поздних версий при вызове метода `RSA.Create(384)` создается исключение, указывающее на то, что размер слишком мал.</span><span class="sxs-lookup"><span data-stu-id="2162a-106">In .NET Core 3.0 and later versions, the method call `RSA.Create(384)` throws an exception indicating the size is too small.</span></span>

<span data-ttu-id="2162a-107">Изменения были внесены, так как для OpenSSL, где выполняются криптографические операции в Linux, между выпусками версий 1.1.0 и 1.0.2 увеличено минимальное значение.</span><span class="sxs-lookup"><span data-stu-id="2162a-107">This changes was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0.</span></span>  <span data-ttu-id="2162a-108">В .NET Core 3.0 предпочтительно использовать OpenSSL версий от 1.1.x до 1.0.x. Передаваемый номер версии был повышен в соответствии с повышением лимита для зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2162a-108">.NET Core 3.0 prefers OpenSSL 1.1.x to 1.0.x, and the minimum reported version was raised to reflect this new higher dependency limitation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2162a-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="2162a-109">Version introduced</span></span>

<span data-ttu-id="2162a-110">3.0</span><span class="sxs-lookup"><span data-stu-id="2162a-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2162a-111">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="2162a-111">Recommended action</span></span>

<span data-ttu-id="2162a-112">Если вы вызываете любой затронутый API-интерфейс, убедитесь, что размер созданных ключей не меньше минимального значения, установленного поставщиком.</span><span class="sxs-lookup"><span data-stu-id="2162a-112">If you call any of the affected APIs, ensure that the size of any generated keys is not less than the provider minimum.</span></span>

> [!NOTE]
> <span data-ttu-id="2162a-113">Стандарт 384-битового шифрования RSA уже считается небезопасным (как и стандарт 512-битового шифрования).</span><span class="sxs-lookup"><span data-stu-id="2162a-113">384-bit RSA is already considered insecure (as is 512-bit RSA).</span></span> <span data-ttu-id="2162a-114">В современных документах, таких как [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf) (Специальная публикация NIST 800-57, часть 1, редакция 4), рекомендуется создавать ключи с минимальным размером 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="2162a-114">Modern recommendations, such as [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggest 2048-bit as the minimum size for newly generated keys.</span></span>

#### <a name="category"></a><span data-ttu-id="2162a-115">Категория</span><span class="sxs-lookup"><span data-stu-id="2162a-115">Category</span></span>

<span data-ttu-id="2162a-116">Шифрование</span><span class="sxs-lookup"><span data-stu-id="2162a-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2162a-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2162a-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`


-->
