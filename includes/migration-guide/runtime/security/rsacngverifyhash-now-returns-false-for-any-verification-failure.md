---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887828"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="91181-101">RSACng.VerifyHash теперь возвращает значение False при любом сбое проверки</span><span class="sxs-lookup"><span data-stu-id="91181-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="91181-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="91181-102">Details</span></span>|<span data-ttu-id="91181-103">Начиная с .NET Framework 4.6.2 этот метод возвращает **False**, если сама подпись неверно форматирована.</span><span class="sxs-lookup"><span data-stu-id="91181-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="91181-104">Теперь он возвращает значение false при любом сбое проверки. В .NET Framework 4.6 и 4.6.1 этот метод выдает <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, если сама подпись имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="91181-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="91181-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="91181-105">Suggestion</span></span>|<span data-ttu-id="91181-106">Любой код, выполнение которого зависит от обработки <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает **False**.</span><span class="sxs-lookup"><span data-stu-id="91181-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns **False**.</span></span>|
|<span data-ttu-id="91181-107">Область</span><span class="sxs-lookup"><span data-stu-id="91181-107">Scope</span></span>|<span data-ttu-id="91181-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="91181-108">Minor</span></span>|
|<span data-ttu-id="91181-109">Version</span><span class="sxs-lookup"><span data-stu-id="91181-109">Version</span></span>|<span data-ttu-id="91181-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="91181-110">4.6.2</span></span>|
|<span data-ttu-id="91181-111">Type</span><span class="sxs-lookup"><span data-stu-id="91181-111">Type</span></span>|<span data-ttu-id="91181-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="91181-112">Runtime</span></span>|
|<span data-ttu-id="91181-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="91181-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
