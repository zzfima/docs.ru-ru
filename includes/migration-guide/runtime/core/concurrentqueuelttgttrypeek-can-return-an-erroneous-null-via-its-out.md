---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236715"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue\<T>.TryPeek может возвращать ошибочные значения NULL в выходном параметре

|   |   |
|---|---|
|Подробные сведения|В некоторых сценариях с несколькими потоками <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> может возвращать значение true, но заполнять выходной параметр значением NULL (вместо правильного значения).|
|Предложение|Эта проблема решена в EntityFramework 4.5.1. Чтобы устранить проблему, выполните обновление до этой версии платформы.|
|Область|Значительно|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
