---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988502"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="58219-101">Microsoft.VisualBasic.Constants.vbNewLine устарела</span><span class="sxs-lookup"><span data-stu-id="58219-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="58219-102">Константа <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> помечена как [Obsolete](xref:System.ObsoleteAttribute) (Устаревшая) в .NET Framework, но ранее соответствующий атрибут отсутствовал в библиотеке .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="58219-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) in .NET Framework, but the attribute was missing previously in the .NET Core 3.0 library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="58219-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="58219-103">Version introduced</span></span>

<span data-ttu-id="58219-104">.NET Core 3.0 (предварительная версия 8)</span><span class="sxs-lookup"><span data-stu-id="58219-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="58219-105">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="58219-105">Details</span></span>

<span data-ttu-id="58219-106">Начиная с .NET Core 3.0 (предварительная версия 8) атрибут [Obsolete](xref:System.ObsoleteAttribute) был применен к константе <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> для обеспечения соответствия `vbNewLine` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58219-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant to conform to `vbNewLine` in the .NET Framework.</span></span> <span data-ttu-id="58219-107">При использовании константы `vbNewLine` выдается предупреждение компилятора.</span><span class="sxs-lookup"><span data-stu-id="58219-107">Use of the `vbNewLine` constant produces a compiler warning.</span></span> 

<span data-ttu-id="58219-108">В предыдущих версиях .NET Core `vbNewLine` не вызывает предупреждение компилятора.</span><span class="sxs-lookup"><span data-stu-id="58219-108">In previous versions of .NET Core, `vbNewLine` did not produce a compiler warning.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="58219-109">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="58219-109">Recommended action</span></span>

<span data-ttu-id="58219-110">Сообщение атрибута [Obsolete](xref:System.ObsoleteAttribute) для `vbNewLine` включает следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="58219-110">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="58219-111">Для возврата каретки и перевода строки используйте [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span><span class="sxs-lookup"><span data-stu-id="58219-111">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="58219-112">Для новой строки на текущей платформе используйте <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="58219-112">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="58219-113">Категория</span><span class="sxs-lookup"><span data-stu-id="58219-113">Category</span></span>

<span data-ttu-id="58219-114">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="58219-114">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="58219-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="58219-115">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

