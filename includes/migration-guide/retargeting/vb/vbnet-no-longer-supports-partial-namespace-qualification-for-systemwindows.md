---
ms.openlocfilehash: 43e9c1c2f03daedf4d56152da5672b89399a3c69
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804681"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="08ec5-101">VB.NET больше не поддерживает частичные квалификации пространства имен для API-интерфейсов System.Windows</span><span class="sxs-lookup"><span data-stu-id="08ec5-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="08ec5-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="08ec5-102">Details</span></span>|<span data-ttu-id="08ec5-103">Начиная с .NET Framework 4.5.2 в проектах VB.NET невозможно задать API-интерфейсы System.Windows с частично указанными пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="08ec5-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="08ec5-104">Например, ссылка на <code>Windows.Forms.DialogResult</code> завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="08ec5-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="08ec5-105">Вместо этого код должен ссылаться на полное доменное имя (<xref:System.Windows.Forms.DialogResult>) или импортировать конкретное пространство имен и сослаться просто на <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="08ec5-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="08ec5-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="08ec5-106">Suggestion</span></span>|<span data-ttu-id="08ec5-107">Следует обновить код для ссылки на API <code>System.Windows</code> либо с простыми именами (и импортом соответствующего пространства имен), либо с полными доменными именами.</span><span class="sxs-lookup"><span data-stu-id="08ec5-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="08ec5-108">Область</span><span class="sxs-lookup"><span data-stu-id="08ec5-108">Scope</span></span>|<span data-ttu-id="08ec5-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="08ec5-109">Minor</span></span>|
|<span data-ttu-id="08ec5-110">Версия</span><span class="sxs-lookup"><span data-stu-id="08ec5-110">Version</span></span>|<span data-ttu-id="08ec5-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="08ec5-111">4.5.2</span></span>|
|<span data-ttu-id="08ec5-112">Тип</span><span class="sxs-lookup"><span data-stu-id="08ec5-112">Type</span></span>|<span data-ttu-id="08ec5-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="08ec5-113">Retargeting</span></span>|

