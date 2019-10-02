---
ms.openlocfilehash: 82835915efa0e113e81bb09bd5062ee3252f2a64
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216975"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="acb1c-101">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="acb1c-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="acb1c-102">Класс <xref:System.ComponentModel.InvalidAsynchronousStateException> перемещен.</span><span class="sxs-lookup"><span data-stu-id="acb1c-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="acb1c-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="acb1c-103">Change description</span></span>

<span data-ttu-id="acb1c-104">В .NET Core 2.2 и более ранних версиях класс <xref:System.ComponentModel.InvalidAsynchronousStateException> находится в сборке *System.ComponentModel.TypeConverter*.</span><span class="sxs-lookup"><span data-stu-id="acb1c-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="acb1c-105">Начиная с .NET Core 3.0, он находится в сборке *System.ComponentModel.Primitives*.</span><span class="sxs-lookup"><span data-stu-id="acb1c-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="acb1c-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="acb1c-106">Version introduced</span></span>

<span data-ttu-id="acb1c-107">3.0</span><span class="sxs-lookup"><span data-stu-id="acb1c-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="acb1c-108">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="acb1c-108">Recommended action</span></span>

<span data-ttu-id="acb1c-109">Это изменение влияет только на приложения, использующие отражение для загрузки <xref:System.ComponentModel.InvalidAsynchronousStateException> путем вызова метода, такого как <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, или перегрузки <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>, которая предполагает, что тип находится в определенной сборке.</span><span class="sxs-lookup"><span data-stu-id="acb1c-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="acb1c-110">В этом случае сборку, указанную в вызове метода, необходимо обновить в соответствии с новым расположением сборки типа.</span><span class="sxs-lookup"><span data-stu-id="acb1c-110">If that is the case, the assembly the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="acb1c-111">Категория</span><span class="sxs-lookup"><span data-stu-id="acb1c-111">Category</span></span>

<span data-ttu-id="acb1c-112">CoreFX</span><span class="sxs-lookup"><span data-stu-id="acb1c-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="acb1c-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="acb1c-113">Affected APIs</span></span>

- <span data-ttu-id="acb1c-114">Нет</span><span class="sxs-lookup"><span data-stu-id="acb1c-114">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
