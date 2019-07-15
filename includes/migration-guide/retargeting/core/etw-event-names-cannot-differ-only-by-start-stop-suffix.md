---
ms.openlocfilehash: 9ad283af76085c228bedceb6db723a1d18b10210
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804407"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="be4a2-101">Имена событий в трассировке событий Windows не должны отличаться друг от друга только суффиксами "Start" или "Stop"</span><span class="sxs-lookup"><span data-stu-id="be4a2-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="be4a2-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="be4a2-102">Details</span></span>|<span data-ttu-id="be4a2-103">В .NET Framework 4.6 и 4.6.1 среда выполнения вызывает исключение <xref:System.ArgumentException> в случае, когда имена двух событий в трассировке событий Windows отличаются только суффиксами &quot;Start&quot; или &quot;Stop&quot; (например, одно событие с именем <code>LogUser</code>, а другое с именем <code>LogUserStart</code>).</span><span class="sxs-lookup"><span data-stu-id="be4a2-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="be4a2-104">В этом случае среда выполнения не может определить источник событий и, соответственно, сделать запись в журнале.</span><span class="sxs-lookup"><span data-stu-id="be4a2-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="be4a2-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="be4a2-105">Suggestion</span></span>|<span data-ttu-id="be4a2-106">Чтобы не возникло исключение, убедитесь, что имена событий не отличаются только суффиксами &quot;Start&quot; или &quot;Stop&quot;. Это требование снято начиная с версии .NET Framework 4.6.2. Среда выполнения может устранить неоднозначность имен событий, которые отличаются только суффиксами &quot;Start&quot; и &quot;Stop&quot;.</span><span class="sxs-lookup"><span data-stu-id="be4a2-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="be4a2-107">Область</span><span class="sxs-lookup"><span data-stu-id="be4a2-107">Scope</span></span>|<span data-ttu-id="be4a2-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="be4a2-108">Edge</span></span>|
|<span data-ttu-id="be4a2-109">Версия</span><span class="sxs-lookup"><span data-stu-id="be4a2-109">Version</span></span>|<span data-ttu-id="be4a2-110">4.6</span><span class="sxs-lookup"><span data-stu-id="be4a2-110">4.6</span></span>|
|<span data-ttu-id="be4a2-111">Тип</span><span class="sxs-lookup"><span data-stu-id="be4a2-111">Type</span></span>|<span data-ttu-id="be4a2-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="be4a2-112">Retargeting</span></span>|

