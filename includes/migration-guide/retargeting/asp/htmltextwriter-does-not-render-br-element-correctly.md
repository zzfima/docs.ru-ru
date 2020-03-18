---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804523"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="058c2-101">HtmlTextWriter неправильно отображает элемент `<br/>`</span><span class="sxs-lookup"><span data-stu-id="058c2-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="058c2-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="058c2-102">Details</span></span>|<span data-ttu-id="058c2-103">Начиная с .NET Framework 4.6, при вызове <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> и <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> с элементом <code>&lt;BR /&gt;</code> правильно вставляется только один <code>&lt;BR /&gt;</code> (вместо двух).</span><span class="sxs-lookup"><span data-stu-id="058c2-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="058c2-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="058c2-104">Suggestion</span></span>|<span data-ttu-id="058c2-105">Если приложение зависит от дополнительного тега <code>&lt;BR /&gt;</code>, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> следует вызвать второй раз.</span><span class="sxs-lookup"><span data-stu-id="058c2-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="058c2-106">Обратите внимание, что это изменение поведения влияет только на приложения, предназначенные для .NET Framework 4.6 или более поздних версий, поэтому другим вариантом является нацеливание на предыдущую версию платформы .NET Framework для получения старого поведения.</span><span class="sxs-lookup"><span data-stu-id="058c2-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="058c2-107">Область</span><span class="sxs-lookup"><span data-stu-id="058c2-107">Scope</span></span>|<span data-ttu-id="058c2-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="058c2-108">Edge</span></span>|
|<span data-ttu-id="058c2-109">Version</span><span class="sxs-lookup"><span data-stu-id="058c2-109">Version</span></span>|<span data-ttu-id="058c2-110">4.6</span><span class="sxs-lookup"><span data-stu-id="058c2-110">4.6</span></span>|
|<span data-ttu-id="058c2-111">Type</span><span class="sxs-lookup"><span data-stu-id="058c2-111">Type</span></span>|<span data-ttu-id="058c2-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="058c2-112">Retargeting</span></span>|
|<span data-ttu-id="058c2-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="058c2-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|
