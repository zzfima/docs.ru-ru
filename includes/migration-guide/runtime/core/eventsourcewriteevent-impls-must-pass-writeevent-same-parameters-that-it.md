---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235431"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="6c48d-101">Реализация EventSource.WriteEvent должна передавать WriteEvent те же параметры, которые она получила (плюс идентификатор)</span><span class="sxs-lookup"><span data-stu-id="6c48d-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6c48d-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="6c48d-102">Details</span></span>|<span data-ttu-id="6c48d-103">В среде выполнения теперь реализуется контракт, определяющий следующее: класс, производный от <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> и определяющий метод событий ETW, должен вызвать метод <code>EventSource.WriteEvent</code> базового класса с идентификатором события и теми же аргументами, с которыми был передан метод событий ETW.</span><span class="sxs-lookup"><span data-stu-id="6c48d-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>|
|<span data-ttu-id="6c48d-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="6c48d-104">Suggestion</span></span>|<span data-ttu-id="6c48d-105">Возникает исключение <xref:System.IndexOutOfRangeException?displayProperty=name>, если объект <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> считывает данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> в процессе для источника события, нарушающего контракт.</span><span class="sxs-lookup"><span data-stu-id="6c48d-105">An <xref:System.IndexOutOfRangeException?displayProperty=name> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> data in process for an event source that violates this contract.</span></span>|
|<span data-ttu-id="6c48d-106">Область</span><span class="sxs-lookup"><span data-stu-id="6c48d-106">Scope</span></span>|<span data-ttu-id="6c48d-107">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="6c48d-107">Minor</span></span>|
|<span data-ttu-id="6c48d-108">Версия</span><span class="sxs-lookup"><span data-stu-id="6c48d-108">Version</span></span>|<span data-ttu-id="6c48d-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="6c48d-109">4.5.1</span></span>|
|<span data-ttu-id="6c48d-110">Тип</span><span class="sxs-lookup"><span data-stu-id="6c48d-110">Type</span></span>|<span data-ttu-id="6c48d-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="6c48d-111">Runtime</span></span>|
