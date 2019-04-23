---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804942"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="b342d-101">Реализация EventSource.WriteEvent должна передавать WriteEvent те же параметры, которые она получила (плюс идентификатор)</span><span class="sxs-lookup"><span data-stu-id="b342d-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b342d-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b342d-102">Details</span></span>|<span data-ttu-id="b342d-103">В среде выполнения теперь реализуется контракт, определяющий следующее: класс, производный от <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> и определяющий метод событий ETW, должен вызвать метод <code>EventSource.WriteEvent</code> базового класса с идентификатором события и теми же аргументами, с которыми был передан метод событий ETW.</span><span class="sxs-lookup"><span data-stu-id="b342d-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>|
|<span data-ttu-id="b342d-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="b342d-104">Suggestion</span></span>|<span data-ttu-id="b342d-105">Возникает исключение <xref:System.IndexOutOfRangeException?displayProperty=name>, если объект <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> считывает данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> в процессе для источника события, нарушающего контракт.</span><span class="sxs-lookup"><span data-stu-id="b342d-105">An <xref:System.IndexOutOfRangeException?displayProperty=name> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> data in process for an event source that violates this contract.</span></span>|
|<span data-ttu-id="b342d-106">Область</span><span class="sxs-lookup"><span data-stu-id="b342d-106">Scope</span></span>|<span data-ttu-id="b342d-107">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="b342d-107">Minor</span></span>|
|<span data-ttu-id="b342d-108">Версия</span><span class="sxs-lookup"><span data-stu-id="b342d-108">Version</span></span>|<span data-ttu-id="b342d-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="b342d-109">4.5.1</span></span>|
|<span data-ttu-id="b342d-110">Тип</span><span class="sxs-lookup"><span data-stu-id="b342d-110">Type</span></span>|<span data-ttu-id="b342d-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="b342d-111">Runtime</span></span>|
