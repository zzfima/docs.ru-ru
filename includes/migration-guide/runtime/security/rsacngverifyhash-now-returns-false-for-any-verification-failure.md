---
ms.openlocfilehash: 7d60578ac2913037e1cdeda329f06f9a4986574d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857547"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="fdcf2-101">RSACng.VerifyHash теперь возвращает значение False при любом сбое проверки</span><span class="sxs-lookup"><span data-stu-id="fdcf2-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fdcf2-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="fdcf2-102">Details</span></span>|<span data-ttu-id="fdcf2-103">Начиная с .NET Framework 4.6.2 этот метод возвращает <strong>False</strong>, если сама подпись неверно форматирована.</span><span class="sxs-lookup"><span data-stu-id="fdcf2-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="fdcf2-104">Теперь он возвращает значение false при любом сбое проверки. В .NET Framework 4.6 и 4.6.1 этот метод выдает <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, если сама подпись имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="fdcf2-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="fdcf2-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="fdcf2-105">Suggestion</span></span>|<span data-ttu-id="fdcf2-106">Любой код, выполнение которого зависит от обработки <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="fdcf2-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="fdcf2-107">Область</span><span class="sxs-lookup"><span data-stu-id="fdcf2-107">Scope</span></span>|<span data-ttu-id="fdcf2-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="fdcf2-108">Minor</span></span>|
|<span data-ttu-id="fdcf2-109">Версия</span><span class="sxs-lookup"><span data-stu-id="fdcf2-109">Version</span></span>|<span data-ttu-id="fdcf2-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="fdcf2-110">4.6.2</span></span>|
|<span data-ttu-id="fdcf2-111">Тип</span><span class="sxs-lookup"><span data-stu-id="fdcf2-111">Type</span></span>|<span data-ttu-id="fdcf2-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="fdcf2-112">Runtime</span></span>|
|<span data-ttu-id="fdcf2-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="fdcf2-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

