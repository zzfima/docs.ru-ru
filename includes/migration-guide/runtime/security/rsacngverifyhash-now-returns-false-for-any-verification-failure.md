---
ms.openlocfilehash: 7d60578ac2913037e1cdeda329f06f9a4986574d
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760695"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="9c560-101">RSACng.VerifyHash теперь возвращает значение False при любом сбое проверки</span><span class="sxs-lookup"><span data-stu-id="9c560-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9c560-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9c560-102">Details</span></span>|<span data-ttu-id="9c560-103">Начиная с .NET Framework 4.6.2 этот метод возвращает <strong>False</strong>, если сама подпись неверно форматирована.</span><span class="sxs-lookup"><span data-stu-id="9c560-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="9c560-104">Теперь он возвращает значение false при любом сбое проверки. В .NET Framework 4.6 и 4.6.1 этот метод выдает <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, если сама подпись имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="9c560-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="9c560-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="9c560-105">Suggestion</span></span>|<span data-ttu-id="9c560-106">Любой код, выполнение которого зависит от обработки <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="9c560-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="9c560-107">Область</span><span class="sxs-lookup"><span data-stu-id="9c560-107">Scope</span></span>|<span data-ttu-id="9c560-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="9c560-108">Minor</span></span>|
|<span data-ttu-id="9c560-109">Версия</span><span class="sxs-lookup"><span data-stu-id="9c560-109">Version</span></span>|<span data-ttu-id="9c560-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="9c560-110">4.6.2</span></span>|
|<span data-ttu-id="9c560-111">Тип</span><span class="sxs-lookup"><span data-stu-id="9c560-111">Type</span></span>|<span data-ttu-id="9c560-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="9c560-112">Runtime</span></span>|
|<span data-ttu-id="9c560-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="9c560-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

