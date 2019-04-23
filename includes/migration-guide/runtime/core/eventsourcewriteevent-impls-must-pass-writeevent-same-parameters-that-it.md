---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235431"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>Реализация EventSource.WriteEvent должна передавать WriteEvent те же параметры, которые она получила (плюс идентификатор)

|   |   |
|---|---|
|Подробные сведения|В среде выполнения теперь реализуется контракт, определяющий следующее: класс, производный от <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> и определяющий метод событий ETW, должен вызвать метод <code>EventSource.WriteEvent</code> базового класса с идентификатором события и теми же аргументами, с которыми был передан метод событий ETW.|
|Предложение|Возникает исключение <xref:System.IndexOutOfRangeException?displayProperty=name>, если объект <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> считывает данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> в процессе для источника события, нарушающего контракт.|
|Область|Дополнительный номер|
|Версия|4.5.1|
|Тип|Среда выполнения|
