---
ms.openlocfilehash: 95a4c807f5c1077cf52f54b196e904ebc98c32f8
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116366"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="8fb87-101">Microsoft.VisualBasic.Constants.vbNewLine устарела</span><span class="sxs-lookup"><span data-stu-id="8fb87-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="8fb87-102">Начиная с .NET Core 3.0 (предварительная версия 8) константа <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> помечена как [\[устаревшая\]](xref:System.ObsoleteAttribute).</span><span class="sxs-lookup"><span data-stu-id="8fb87-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked as [\[Obsolete\]](xref:System.ObsoleteAttribute) starting with .NET Core 3.0 Preview 8.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8fb87-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="8fb87-103">Version introduced</span></span>

<span data-ttu-id="8fb87-104">3.0 (предварительная версия 8)</span><span class="sxs-lookup"><span data-stu-id="8fb87-104">3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="8fb87-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="8fb87-105">Change description</span></span>

<span data-ttu-id="8fb87-106">Начиная с .NET Core 3.0 (предварительная версия 8), к константе <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> применяется атрибут [Obsolete](xref:System.ObsoleteAttribute).</span><span class="sxs-lookup"><span data-stu-id="8fb87-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant.</span></span> <span data-ttu-id="8fb87-107">При использовании константы выдается предупреждение компилятора.</span><span class="sxs-lookup"><span data-stu-id="8fb87-107">Use of the constant produces a compiler warning.</span></span> <span data-ttu-id="8fb87-108">В .NET Framework и предыдущих версиях .NET Core она не была помечена как устаревшая.</span><span class="sxs-lookup"><span data-stu-id="8fb87-108">In .NET Framework and previous releases of .NET Core, it was not marked as obsolete.</span></span>

<span data-ttu-id="8fb87-109">Это изменение было внесено для поддержки Visual Basic в качестве языка для разработки на нескольких платформах.</span><span class="sxs-lookup"><span data-stu-id="8fb87-109">This change was made to support Visual Basic as a language for multi-platform development.</span></span> <span data-ttu-id="8fb87-110">Константа <xref:Microsoft.VisualBasic.Constants.vbNewLine> эквивалентна `\r\n`, последовательности символов новой строки в Windows.</span><span class="sxs-lookup"><span data-stu-id="8fb87-110">The <xref:Microsoft.VisualBasic.Constants.vbNewLine> constant is equivalent to `\r\n`, the newline character sequence on Windows.</span></span> <span data-ttu-id="8fb87-111">В системах на основе Unix символ новой строки — `\n`.</span><span class="sxs-lookup"><span data-stu-id="8fb87-111">On Unix-based systems, the newline character is `\n`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8fb87-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="8fb87-112">Recommended action</span></span>

<span data-ttu-id="8fb87-113">Сообщение атрибута [Obsolete](xref:System.ObsoleteAttribute) для <xref:Microsoft.VisualBasic.Constants.vbNewLine> включает следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="8fb87-113">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for <xref:Microsoft.VisualBasic.Constants.vbNewLine> includes the following recommendation:</span></span>

<span data-ttu-id="8fb87-114">Для возврата каретки и перевода строки используйте <xref:Microsoft.VisualBasic.Constants.vbCrLf>.</span><span class="sxs-lookup"><span data-stu-id="8fb87-114">For a carriage return and line feed, use <xref:Microsoft.VisualBasic.Constants.vbCrLf>.</span></span> <span data-ttu-id="8fb87-115">Для новой строки на текущей платформе используйте <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8fb87-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="8fb87-116">Категория</span><span class="sxs-lookup"><span data-stu-id="8fb87-116">Category</span></span>

<span data-ttu-id="8fb87-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8fb87-117">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8fb87-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="8fb87-118">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
