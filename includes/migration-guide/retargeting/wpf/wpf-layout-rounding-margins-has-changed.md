---
ms.openlocfilehash: 73096e5f61e5257e062df9743cae0f5464892357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804562"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a>Изменились параметры округления полей макета WPF

|   |   |
|---|---|
|Подробнее|Способ округления полей, а также их границ и фона, изменен. В результате этого изменения:<ul><li>ширина или высота элементов может увеличиться или уменьшиться максимум на один пиксель;</li><li>расположение объекта может измениться максимум на один пиксель;</li><li>выровненные по центру элементы могут сместиться по вертикали или горизонтали максимум на один пиксель.</li></ul>По умолчанию новый макет включен только для приложений, предназначенных для .NET Framework 4.6.|
|Предложение|Поскольку это изменение, как правило, приводит к устранению обрезки правых или нижних элементов управления WPF при высоком разрешении, для приложений, предназначенных для более ранних версий .NET Framework, но выполняющихся в .NET Framework 4.6, можно выбрать это новое поведение, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config.<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>Для приложений, предназначенных для .NET Framework 4.6, в которых требуется задать отрисовку элементов управления WPF с помощью прежнего алгоритма макета, можно добавить следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Version|4.6|
|Type|Изменение целевой платформы|
