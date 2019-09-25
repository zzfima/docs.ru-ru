---
ms.openlocfilehash: 07ab65de16b72bd0844a39e4b35235c5f043f3ec
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117178"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a>Увеличен минимальный размер создаваемых ключей RSAOpenSsl

Минимальный размер создаваемых ключей RSA в Linux увеличен с 384 до 512 бит.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Core 3.0, минимальный допустимый размер ключа, передаваемый свойством `LegalKeySizes` в экземплярах RSA из <System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType> и <System.Security.Cryptography.RSACryptoServicePlatform.%23ctor%2A?displayProperty=nameWithType> в Linux, увеличен с 384 до 512 бит.

В результате в .NET Core 2.2 и более ранних версий вызов такого метода, как `RSA.Create(384)`, выполняется успешно. В .NET Core 3.0 и более поздних версий при вызове метода `RSA.Create(384)` создается исключение, указывающее на то, что размер слишком мал.

Изменения были внесены, так как для OpenSSL, где выполняются криптографические операции в Linux, между выпусками версий 1.1.0 и 1.0.2 увеличено минимальное значение.  В .NET Core 3.0 предпочтительно использовать OpenSSL версий от 1.1.x до 1.0.x. Передаваемый номер версии был повышен в соответствии с повышением лимита для зависимостей.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

Если вы вызываете любой затронутый API-интерфейс, убедитесь, что размер созданных ключей не меньше минимального значения, установленного поставщиком.

> [!NOTE]
> Стандарт 384-битового шифрования RSA уже считается небезопасным (как и стандарт 512-битового шифрования). В современных документах, таких как [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf) (Специальная публикация NIST 800-57, часть 1, редакция 4), рекомендуется создавать ключи с минимальным размером 2048 бит.

#### <a name="category"></a>Категория

Шифрование

#### <a name="affected-apis"></a>Затронутые API

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
