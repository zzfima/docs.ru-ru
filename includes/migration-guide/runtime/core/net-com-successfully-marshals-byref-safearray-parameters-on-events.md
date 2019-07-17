---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802648"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM успешно маршалирует параметры ByRef SafeArray в события

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7.2 и более ранних версиях параметр ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) события COM не позволял выполнить маршалинг обратно в машинный код.  Благодаря этому изменению [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) теперь успешно маршалируется.<ul><li>[x] Режим совместимости</li></ul>|
|Предложение|Если правильный маршалинг параметров ByRef SafeArray в событиях COM нарушает выполнение, этот код можно отключить, добавив следующий параметр конфигурации в файл конфигурации приложения:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.8|
|Тип|Среда выполнения|

