---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003017"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a><span data-ttu-id="91fdd-101">Изменение доступа для AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="91fdd-101">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>

<span data-ttu-id="91fdd-102">Начиная с .NET Core 3.0 RC1 (релиз-кандидат 1) специальные возможности `AccessibleObject.RuntimeIDFirstItem` изменились с `protected` на `internal`.</span><span class="sxs-lookup"><span data-stu-id="91fdd-102">Starting in .NET Core 3.0 RC1, the accessibility of `AccessibleObject.RuntimeIDFirstItem` has changed from `protected` to `internal`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="91fdd-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="91fdd-103">Change description</span></span>

<span data-ttu-id="91fdd-104">Начиная с .NET Core 3.0 (предварительная версия 4) поле `AccessibleObject.RuntimeIDFirstItem` было `protected`.</span><span class="sxs-lookup"><span data-stu-id="91fdd-104">Starting with .NET Core 3.0 Preview 4, the `AccessibleObject.RuntimeIDFirstItem` field was `protected`.</span></span> <span data-ttu-id="91fdd-105">Начиная с версии .NET Core 3.0 RC1 (релиз-кандидат 1) оно изменилось с `protected` на `internal` в соответствии со специальными возможностями этого поля в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="91fdd-105">Starting with .NET Core 3.0 RC1, it has changed from `protected` to `internal` to align with the accessibility of the field in the .NET Framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="91fdd-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="91fdd-106">Version introduced</span></span>

<span data-ttu-id="91fdd-107">3.0 RC1 (релиз-кандидат 1)</span><span class="sxs-lookup"><span data-stu-id="91fdd-107">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="91fdd-108">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="91fdd-108">Recommended action</span></span>

<span data-ttu-id="91fdd-109">Это изменение может повлиять на вас, если вы разработали приложение .NET Core с типом, который является производным от <xref:System.Windows.Forms.AccessibleObject> и обращается к полю `RuntimeIDFirstItem`.</span><span class="sxs-lookup"><span data-stu-id="91fdd-109">The change can affect you if you've developed a .NET Core app with a type that derives from <xref:System.Windows.Forms.AccessibleObject> and accesses the `RuntimeIDFirstItem` field.</span></span> <span data-ttu-id="91fdd-110">В этом случае локальную константу можно определить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="91fdd-110">If this is the case, you can define a local constant as follows:</span></span>

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a><span data-ttu-id="91fdd-111">Категория</span><span class="sxs-lookup"><span data-stu-id="91fdd-111">Category</span></span>

<span data-ttu-id="91fdd-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91fdd-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="91fdd-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="91fdd-113">Affected APIs</span></span>

- <span data-ttu-id="91fdd-114">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="91fdd-114">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
