---
ms.openlocfilehash: 82835915efa0e113e81bb09bd5062ee3252f2a64
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568120"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="d6208-101">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="d6208-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="d6208-102">Класс <xref:System.ComponentModel.InvalidAsynchronousStateException> перемещен.</span><span class="sxs-lookup"><span data-stu-id="d6208-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d6208-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="d6208-103">Change description</span></span>

<span data-ttu-id="d6208-104">В .NET Core 2.2 и более ранних версиях класс <xref:System.ComponentModel.InvalidAsynchronousStateException> находится в сборке *System.ComponentModel.TypeConverter*.</span><span class="sxs-lookup"><span data-stu-id="d6208-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="d6208-105">Начиная с .NET Core 3.0, он находится в сборке *System.ComponentModel.Primitives*.</span><span class="sxs-lookup"><span data-stu-id="d6208-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d6208-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="d6208-106">Version introduced</span></span>

<span data-ttu-id="d6208-107">3.0</span><span class="sxs-lookup"><span data-stu-id="d6208-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d6208-108">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="d6208-108">Recommended action</span></span>

<span data-ttu-id="d6208-109">Это изменение влияет только на приложения, использующие отражение для загрузки <xref:System.ComponentModel.InvalidAsynchronousStateException> путем вызова метода, такого как <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, или перегрузки <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>, которая предполагает, что тип находится в определенной сборке.</span><span class="sxs-lookup"><span data-stu-id="d6208-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="d6208-110">В этом случае сборку, указанную в вызове метода, необходимо обновить в соответствии с новым расположением сборки типа.</span><span class="sxs-lookup"><span data-stu-id="d6208-110">If that is the case, the assembly the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="d6208-111">Категория</span><span class="sxs-lookup"><span data-stu-id="d6208-111">Category</span></span>

<span data-ttu-id="d6208-112">CoreFX</span><span class="sxs-lookup"><span data-stu-id="d6208-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d6208-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d6208-113">Affected APIs</span></span>

- <span data-ttu-id="d6208-114">Нет</span><span class="sxs-lookup"><span data-stu-id="d6208-114">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
