---
ms.openlocfilehash: 2a751acc129ebd1c917b87f8083ffef72c7d8c17
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568179"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="df18c-101">Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла</span><span class="sxs-lookup"><span data-stu-id="df18c-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="df18c-102">Многие интерфейсы API, которые возвращают версию в .NET Core, теперь возвращают версию продукта, а не файла.</span><span class="sxs-lookup"><span data-stu-id="df18c-102">Many of the APIs that return versions in .NET Core now returned the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="df18c-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="df18c-103">Change description</span></span>

<span data-ttu-id="df18c-104">В .NET Core 2.2 и предыдущих версиях такие методы, как <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> и диалоговое окно свойств файла для сборок .NET Core, сообщают версию файла.</span><span class="sxs-lookup"><span data-stu-id="df18c-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="df18c-105">Начиная с версии .NET Core 3.0, они сообщают версию продукта.</span><span class="sxs-lookup"><span data-stu-id="df18c-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="df18c-106">На приведенном ниже рисунке показана разница в сведениях о версии для сборки *System.Runtime.dll* для .NET Core 2.2 (слева) и .NET Core 3.0 (справа), отображаемых в диалоговом окне свойств файла в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="df18c-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![Разница в сведениях о версии](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="df18c-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="df18c-108">Version introduced</span></span>

<span data-ttu-id="df18c-109">3.0</span><span class="sxs-lookup"><span data-stu-id="df18c-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="df18c-110">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="df18c-110">Recommended action</span></span>

<span data-ttu-id="df18c-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="df18c-111">None.</span></span> <span data-ttu-id="df18c-112">Это изменение должно сделать определение версии интуитивно понятным.</span><span class="sxs-lookup"><span data-stu-id="df18c-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="df18c-113">Категория</span><span class="sxs-lookup"><span data-stu-id="df18c-113">Category</span></span>

<span data-ttu-id="df18c-114">CoreFX</span><span class="sxs-lookup"><span data-stu-id="df18c-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="df18c-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="df18c-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
