---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804960"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>Адаптеры потока WinRT больше не вызывают FlushAsync автоматически при закрытии

|   |   |
|---|---|
|Подробные сведения|В приложениях для магазина Windows адаптеры потока среды выполнения Windows больше не вызывают метод FlushAsync из метода Dispose.|
|Предложение|Это изменение должно быть прозрачным. Разработчики могут восстановить прежнее поведение, написав следующий код.<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|Область|Прозрачный|
|Версия|4.5.1|
|Тип|Среда выполнения|
