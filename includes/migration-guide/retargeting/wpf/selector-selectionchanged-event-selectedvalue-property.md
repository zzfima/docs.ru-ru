---
ms.openlocfilehash: e6c93a1bc31c041f36fca3704bca32012a2b42ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859054"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a>Событие SelectionChanged и свойство SelectedValue селектора

|   |   |
|---|---|
|Подробнее|Начиная с .NET Framework 4.7.1 <xref:System.Windows.Controls.Primitives.Selector> всегда обновляет значение своего свойства <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> до порождения события <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> при изменении его выбора. Это позволяет согласовать свойство SelectedValue с другими свойствами выбора (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> и <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), которые изменяются перед порождением события.<p/>В .NET Framework 4.7 и более ранних версий изменение SelectedValue в большинстве случаев происходило до события, но оно выполнялось после события, если изменение выбора было вызвано изменением свойства <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.|
|Предложение|В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, данное изменение можно отключить и использовать устаревшее поведение, добавив следующее в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>В приложениях, предназначенных для .NET Framework 4.7 или более ранней версии, но работающих на платформе .NET Framework 4.7.1 или более поздней версии, можно включить новое поведение, добавив следующее в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Version|4.7.1|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|
