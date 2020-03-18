---
ms.openlocfilehash: 57ca2ad839aab8d61da1a929660920efe1190334
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147540"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a><span data-ttu-id="f69f3-101">Класс TypeDescriptionProviderAttribute перенесен в другую сборку</span><span class="sxs-lookup"><span data-stu-id="f69f3-101">TypeDescriptionProviderAttribute moved to another assembly</span></span>

<span data-ttu-id="f69f3-102">Класс <xref:System.ComponentModel.TypeDescriptionProviderAttribute> перемещен.</span><span class="sxs-lookup"><span data-stu-id="f69f3-102">The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f69f3-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="f69f3-103">Change description</span></span>

<span data-ttu-id="f69f3-104">В .NET Core 2.2 и более ранних версиях класс <xref:System.ComponentModel.TypeDescriptionProviderAttribute> находится в сборке *System.ComponentModel.TypeConverter*.</span><span class="sxs-lookup"><span data-stu-id="f69f3-104">In .NET Core 2.2 and earlier versions, The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="f69f3-105">Начиная с .NET Core 3.0 он находится в сборке *System.ObjectModel*.</span><span class="sxs-lookup"><span data-stu-id="f69f3-105">Starting with .NET Core 3.0, it is found in the *System.ObjectModel* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f69f3-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="f69f3-106">Version introduced</span></span>

<span data-ttu-id="f69f3-107">3,0</span><span class="sxs-lookup"><span data-stu-id="f69f3-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f69f3-108">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="f69f3-108">Recommended action</span></span>

<span data-ttu-id="f69f3-109">Это изменение влияет только на приложения, использующие отражение для загрузки типа <xref:System.ComponentModel.TypeDescriptionProviderAttribute> путем вызова метода, такого как <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, или перегрузки <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>, которая предполагает, что тип находится в определенной сборке.</span><span class="sxs-lookup"><span data-stu-id="f69f3-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.TypeDescriptionProviderAttribute> type by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="f69f3-110">В этом случае сборку, указанную в вызове метода, необходимо обновить в соответствии с новым расположением сборки типа.</span><span class="sxs-lookup"><span data-stu-id="f69f3-110">If that is the case, the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="f69f3-111">Категория</span><span class="sxs-lookup"><span data-stu-id="f69f3-111">Category</span></span>

<span data-ttu-id="f69f3-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f69f3-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f69f3-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f69f3-113">Affected APIs</span></span>

<span data-ttu-id="f69f3-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="f69f3-114">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
