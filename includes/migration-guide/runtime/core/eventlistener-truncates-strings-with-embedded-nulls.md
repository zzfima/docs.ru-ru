---
ms.openlocfilehash: 9084c135769f595491d645e49d24cf507f5f6070
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235881"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener усекает строки с внедренными значениями NULL

|   |   |
|---|---|
|Подробные сведения|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> усекает строки с внедренными значениями NULL. Символы NULL не поддерживаются классом <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name>. Изменение влияет только на приложения, использующие <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> для чтения данных <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> в процессе и значения NULL в качестве разделителей.|
|Предложение|Если возможно, следует обновить данные <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name>, чтобы не использовать внедренные символы NULL.|
|Область|Пограничный случай|
|Версия|4.5.1|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
