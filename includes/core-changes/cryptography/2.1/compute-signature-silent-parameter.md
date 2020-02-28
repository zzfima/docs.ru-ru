---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449232"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a><span data-ttu-id="df445-101">Логический параметр SignedCms.ComputeSignature учитывается</span><span class="sxs-lookup"><span data-stu-id="df445-101">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>

<span data-ttu-id="df445-102">В .NET Core учитывается логический параметр `silent` метода <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df445-102">In .NET Core, the Boolean `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is respected.</span></span> <span data-ttu-id="df445-103">Если этот параметр имеет значение `true`, запрос на ввод ПИН-кода не отображается.</span><span class="sxs-lookup"><span data-stu-id="df445-103">A PIN prompt is not shown if this parameter is set to `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="df445-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="df445-104">Change description</span></span>

<span data-ttu-id="df445-105">В .NET Framework параметр `silent` метода <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> игнорируется, и если поставщик этого требует, запрос на ввод ПИН-кода отображается всегда.</span><span class="sxs-lookup"><span data-stu-id="df445-105">In .NET Framework, the `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is ignored, and a PIN prompt is always shown if required by the provider.</span></span> <span data-ttu-id="df445-106">В .NET Core параметр `silent` учитывается, и если для него задано значение `true`, запрос на ввод ПИН-кода никогда не отображается, даже если этого требует поставщик.</span><span class="sxs-lookup"><span data-stu-id="df445-106">In .NET Core, the `silent` parameter is respected, and if set to `true`, a PIN prompt is never shown, even if it's required by the provider.</span></span>

<span data-ttu-id="df445-107">В .NET Core в версии 2.1 реализована поддержка сообщений CMS/PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="df445-107">Support for CMS/PKCS #7 messages was introduced into .NET Core in version 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="df445-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="df445-108">Version introduced</span></span>

<span data-ttu-id="df445-109">2.1</span><span class="sxs-lookup"><span data-stu-id="df445-109">2.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="df445-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="df445-110">Recommended action</span></span>

<span data-ttu-id="df445-111">Чтобы запрос на ввод ПИН-кода появлялся при необходимости, классические приложения должны вызывать <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> и присваивать логическому параметру значение `false`.</span><span class="sxs-lookup"><span data-stu-id="df445-111">To ensure a PIN prompt appears if required, desktop applications should call <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> and set the Boolean parameter to `false`.</span></span> <span data-ttu-id="df445-112">Полученное поведение аналогично поведению .NET Framework независимо от того, отключен ли в нем тихий контекст.</span><span class="sxs-lookup"><span data-stu-id="df445-112">The resulting behavior is the same as on .NET Framework regardless of whether the silent context is disabled there.</span></span>

### <a name="category"></a><span data-ttu-id="df445-113">Категория</span><span class="sxs-lookup"><span data-stu-id="df445-113">Category</span></span>

<span data-ttu-id="df445-114">Шифрование</span><span class="sxs-lookup"><span data-stu-id="df445-114">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="df445-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="df445-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
