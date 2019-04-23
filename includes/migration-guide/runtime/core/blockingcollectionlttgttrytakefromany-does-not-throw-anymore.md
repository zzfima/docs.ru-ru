---
ms.openlocfilehash: 9e8f9c616d5ae4ed17f35665cff21acbbacda457
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235518"
---
### <a name="blockingcollectionttrytakefromany-does-not-throw-anymore"></a>BlockingCollection\<T>.TryTakeFromAny больше не вызывает исключение

|   |   |
|---|---|
|Подробные сведения|Метод <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> больше не возвращает -1 и <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> больше не вызывает исключение, если одна из коллекций помечена как завершенная. Это изменение позволяет работать с коллекциями, если одна из коллекций пуста или завершена, но другая коллекция по-прежнему содержит элементы, которые можно извлечь.|
|Предложение|Если метод TryTakeFromAny, возвращающий -1, и метод TakeFromAny, создающий исключение, использовались в целях управления потоком при заполнении заблокированной коллекции, такой код следует изменить для использования <code>.Any(b =&gt; b.IsCompleted)</code> для обнаружения этого условия.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li></ul>|
