---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74643931"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a><span data-ttu-id="8c396-101">Изменение доступа для AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="8c396-101">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>

<span data-ttu-id="8c396-102">Начиная с .NET Core 3.0 RC1 (релиз-кандидат 1) специальные возможности `AccessibleObject.RuntimeIDFirstItem` изменились с `protected` на `internal`.</span><span class="sxs-lookup"><span data-stu-id="8c396-102">Starting in .NET Core 3.0 RC1, the accessibility of `AccessibleObject.RuntimeIDFirstItem` has changed from `protected` to `internal`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8c396-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="8c396-103">Change description</span></span>

<span data-ttu-id="8c396-104">Начиная с .NET Core 3.0 (предварительная версия 4) поле `AccessibleObject.RuntimeIDFirstItem` было `protected`.</span><span class="sxs-lookup"><span data-stu-id="8c396-104">Starting with .NET Core 3.0 Preview 4, the `AccessibleObject.RuntimeIDFirstItem` field was `protected`.</span></span> <span data-ttu-id="8c396-105">Начиная с версии .NET Core 3.0 RC1 (релиз-кандидат 1) оно изменилось с `protected` на `internal` в соответствии со специальными возможностями этого поля в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c396-105">Starting with .NET Core 3.0 RC1, it has changed from `protected` to `internal` to align with the accessibility of the field in the .NET Framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8c396-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="8c396-106">Version introduced</span></span>

<span data-ttu-id="8c396-107">3.0 RC1 (релиз-кандидат 1)</span><span class="sxs-lookup"><span data-stu-id="8c396-107">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8c396-108">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="8c396-108">Recommended action</span></span>

<span data-ttu-id="8c396-109">Это изменение может повлиять на вас, если вы разработали приложение .NET Core с типом, который является производным от <xref:System.Windows.Forms.AccessibleObject> и обращается к полю `RuntimeIDFirstItem`.</span><span class="sxs-lookup"><span data-stu-id="8c396-109">The change can affect you if you've developed a .NET Core app with a type that derives from <xref:System.Windows.Forms.AccessibleObject> and accesses the `RuntimeIDFirstItem` field.</span></span> <span data-ttu-id="8c396-110">В этом случае локальную константу можно определить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8c396-110">If this is the case, you can define a local constant as follows:</span></span>

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a><span data-ttu-id="8c396-111">Категория</span><span class="sxs-lookup"><span data-stu-id="8c396-111">Category</span></span>

<span data-ttu-id="8c396-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c396-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8c396-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="8c396-113">Affected APIs</span></span>

- <span data-ttu-id="8c396-114">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="8c396-114">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
