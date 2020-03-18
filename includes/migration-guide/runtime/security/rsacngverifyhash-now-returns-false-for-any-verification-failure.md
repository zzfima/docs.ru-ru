---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887828"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash теперь возвращает значение False при любом сбое проверки

|   |   |
|---|---|
|Подробнее|Начиная с .NET Framework 4.6.2 этот метод возвращает **False**, если сама подпись неверно форматирована. Теперь он возвращает значение false при любом сбое проверки. В .NET Framework 4.6 и 4.6.1 этот метод выдает <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, если сама подпись имеет неправильный формат.|
|Предложение|Любой код, выполнение которого зависит от обработки <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает **False**.|
|Область|Дополнительный номер|
|Version|4.6.2|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
