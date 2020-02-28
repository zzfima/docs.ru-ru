---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449232"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a>Логический параметр SignedCms.ComputeSignature учитывается

В .NET Core учитывается логический параметр `silent` метода <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>. Если этот параметр имеет значение `true`, запрос на ввод ПИН-кода не отображается.

#### <a name="change-description"></a>Описание изменений

В .NET Framework параметр `silent` метода <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> игнорируется, и если поставщик этого требует, запрос на ввод ПИН-кода отображается всегда. В .NET Core параметр `silent` учитывается, и если для него задано значение `true`, запрос на ввод ПИН-кода никогда не отображается, даже если этого требует поставщик.

В .NET Core в версии 2.1 реализована поддержка сообщений CMS/PKCS #7.

#### <a name="version-introduced"></a>Представленная версия

2.1

#### <a name="recommended-action"></a>Рекомендованное действие

Чтобы запрос на ввод ПИН-кода появлялся при необходимости, классические приложения должны вызывать <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> и присваивать логическому параметру значение `false`. Полученное поведение аналогично поведению .NET Framework независимо от того, отключен ли в нем тихий контекст.

### <a name="category"></a>Категория

Шифрование

### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
