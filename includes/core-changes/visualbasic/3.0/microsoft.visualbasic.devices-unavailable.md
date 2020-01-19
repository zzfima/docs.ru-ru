---
ms.openlocfilehash: 7f528510e4158dad71280a7b1f269a231b8c60f2
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116327"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="32a5b-101">Типы из пространства имен Microsoft.VisualBasic.Devices недоступны</span><span class="sxs-lookup"><span data-stu-id="32a5b-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="32a5b-102">Типы в пространстве имен <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> недоступны.</span><span class="sxs-lookup"><span data-stu-id="32a5b-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="32a5b-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="32a5b-103">Version introduced</span></span>

<span data-ttu-id="32a5b-104">.NET Core 3.0 (предварительная версия 8)</span><span class="sxs-lookup"><span data-stu-id="32a5b-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="32a5b-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="32a5b-105">Change description</span></span>

<span data-ttu-id="32a5b-106">Типы из пространства имен <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> были доступны в некоторых предварительных выпусках .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="32a5b-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="32a5b-107">Начиная с предварительной версии 9 .NET Core 3.0, они больше не доступны.</span><span class="sxs-lookup"><span data-stu-id="32a5b-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="32a5b-108">Типы были удалены во избежание ненужных зависимостей сборок или критических изменений в последующих выпусках.</span><span class="sxs-lookup"><span data-stu-id="32a5b-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="32a5b-109">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="32a5b-109">Recommended action</span></span>

<span data-ttu-id="32a5b-110">Если в вашем коде применяются типы <xref:Microsoft.VisualBasic.Devices> и их члены, вы можете использовать соответствующий тип или член из библиотеки классов .NET.</span><span class="sxs-lookup"><span data-stu-id="32a5b-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="32a5b-111">Например, возможности, эквивалентные классу <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType>, предоставляются типами <xref:System.DateTime?displayProperty=nameWithType> и <xref:System.Environment?displayProperty=nameWithType>, а классу <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> — типами в пространстве имен <xref:System.IO.Ports?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="32a5b-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="32a5b-112">Категория</span><span class="sxs-lookup"><span data-stu-id="32a5b-112">Category</span></span>

<span data-ttu-id="32a5b-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32a5b-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="32a5b-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="32a5b-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-->
