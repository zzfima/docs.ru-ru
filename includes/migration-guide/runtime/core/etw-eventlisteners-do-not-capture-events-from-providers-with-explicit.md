---
ms.openlocfilehash: 1ef31202d7c072ca27c21fc22db102aafa6b8de7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858839"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>EventListeners трассировки событий Windows не выполняют запись событий от поставщиков с явными ключевыми словами (например, от поставщика TPL)

|   |   |
|---|---|
|Подробнее|EventListeners трассировки событий Windows с пустой маской ключевого слова неправильно записывают события от поставщиков с явными ключевыми словами. В платформе .NET Framework 4.5 поставщик TPL начал предоставлять явные ключевые слова и привел к возникновению этой проблемы. В .NET Framework 4.6 EventListeners были обновлены, чтобы больше не вызывать эту проблему.|
|Предложение|Чтобы обойти эту проблему, замените вызовы <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> вызовами к перегрузке EnableEvents, которая явно задает маску &quot;любые ключевые слова&quot;: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Пограничный случай|
|Version|4,5|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|
