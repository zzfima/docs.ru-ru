---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887828"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="e82a1-101">RSACng.VerifyHash теперь возвращает значение False при любом сбое проверки</span><span class="sxs-lookup"><span data-stu-id="e82a1-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e82a1-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e82a1-102">Details</span></span>|<span data-ttu-id="e82a1-103">Начиная с .NET Framework 4.6.2 этот метод возвращает **False**, если сама подпись неверно форматирована.</span><span class="sxs-lookup"><span data-stu-id="e82a1-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="e82a1-104">Теперь он возвращает значение false при любом сбое проверки. В .NET Framework 4.6 и 4.6.1 этот метод выдает <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, если сама подпись имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="e82a1-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="e82a1-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="e82a1-105">Suggestion</span></span>|<span data-ttu-id="e82a1-106">Любой код, выполнение которого зависит от обработки <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает **False**.</span><span class="sxs-lookup"><span data-stu-id="e82a1-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns **False**.</span></span>|
|<span data-ttu-id="e82a1-107">Область</span><span class="sxs-lookup"><span data-stu-id="e82a1-107">Scope</span></span>|<span data-ttu-id="e82a1-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="e82a1-108">Minor</span></span>|
|<span data-ttu-id="e82a1-109">Версия</span><span class="sxs-lookup"><span data-stu-id="e82a1-109">Version</span></span>|<span data-ttu-id="e82a1-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="e82a1-110">4.6.2</span></span>|
|<span data-ttu-id="e82a1-111">Тип</span><span class="sxs-lookup"><span data-stu-id="e82a1-111">Type</span></span>|<span data-ttu-id="e82a1-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e82a1-112">Runtime</span></span>|
|<span data-ttu-id="e82a1-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e82a1-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
