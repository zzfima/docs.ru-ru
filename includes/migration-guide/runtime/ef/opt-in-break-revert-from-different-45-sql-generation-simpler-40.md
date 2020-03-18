---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803261"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>Согласие на прерывание для возврата от генерируемого в версии 4.5 кода SQL к более простому коду, генерируемому в версии 4.0

|   |   |
|---|---|
|Подробнее|Запросы, создающие операторы JOIN и содержащие вызов к операции ограничения без предварительного использования OrderBy, теперь создают более простой код SQL. После обновления до .NET Framework 4.5 эти запросы создают более сложный код SQL, чем предыдущие версии.|
|Предложение|Эта функция отключена по умолчанию. Если Entity Framework создает лишние операторы JOIN, что ведет к ухудшению производительности, можно включить эту функцию, добавив следующую запись в раздел <code>&lt;appSettings&gt;</code> файла конфигурации приложения (app.config):<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|Область|Прозрачно|
|Version|4.5.2|
|Type|Параметры выполнения|
