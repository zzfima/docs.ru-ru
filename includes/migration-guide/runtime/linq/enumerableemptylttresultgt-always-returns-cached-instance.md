---
ms.openlocfilehash: c9efbefc2bce9e21f328680795e72b62bfcd5cbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804963"
---
### <a name="enumerableemptytresult-always-returns-cached-instance"></a>Enumerable.Empty\<TResult> всегда возвращает кэшированный экземпляр

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.5 <xref:System.Linq.Enumerable.Empty%60%601> всегда возвращает кэшированный внутренний экземпляр <xref:System.Collections.Generic.IEnumerable%601>. Ранее <xref:System.Linq.Enumerable.Empty%60%601> кэшировал пустой <xref:System.Collections.Generic.IEnumerable%601> в момент вызова API, и в некоторых ситуациях, когда <xref:System.Linq.Enumerable.Empty%60%601> вызывался быстро и параллельно, для различных вызовов API могли возвращаться разные экземпляры типа.|
|Предложение|Так как прежнее поведение было недетерминированным, код вряд ли зависит от него. Однако в том маловероятном случае, когда выполняется сравнение пустых перечислений и ожидается, что они будут неравными, следует создать явные пустые массивы (<code>new T[0]</code>) и не использовать <xref:System.Linq.Enumerable.Empty%60%601>.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
