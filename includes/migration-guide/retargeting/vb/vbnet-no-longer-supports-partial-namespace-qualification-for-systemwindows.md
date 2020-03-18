---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804681"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="f206f-101">VB.NET больше не поддерживает частичные квалификации пространства имен для API-интерфейсов System.Windows</span><span class="sxs-lookup"><span data-stu-id="f206f-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f206f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f206f-102">Details</span></span>|<span data-ttu-id="f206f-103">Начиная с .NET Framework 4.5.2 в проектах VB.NET невозможно задать API-интерфейсы System.Windows с частично указанными пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="f206f-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="f206f-104">Например, ссылка на <code>Windows.Forms.DialogResult</code> завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f206f-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="f206f-105">Вместо этого код должен ссылаться на полное доменное имя (<xref:System.Windows.Forms.DialogResult>) или импортировать конкретное пространство имен и сослаться просто на <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="f206f-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="f206f-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="f206f-106">Suggestion</span></span>|<span data-ttu-id="f206f-107">Следует обновить код для ссылки на API <code>System.Windows</code> либо с простыми именами (и импортом соответствующего пространства имен), либо с полными доменными именами.</span><span class="sxs-lookup"><span data-stu-id="f206f-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="f206f-108">Область</span><span class="sxs-lookup"><span data-stu-id="f206f-108">Scope</span></span>|<span data-ttu-id="f206f-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="f206f-109">Minor</span></span>|
|<span data-ttu-id="f206f-110">Version</span><span class="sxs-lookup"><span data-stu-id="f206f-110">Version</span></span>|<span data-ttu-id="f206f-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="f206f-111">4.5.2</span></span>|
|<span data-ttu-id="f206f-112">Type</span><span class="sxs-lookup"><span data-stu-id="f206f-112">Type</span></span>|<span data-ttu-id="f206f-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="f206f-113">Retargeting</span></span>|
