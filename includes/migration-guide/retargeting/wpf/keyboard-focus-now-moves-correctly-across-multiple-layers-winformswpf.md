---
ms.openlocfilehash: 3bde64b80e5dcfe98bbf598700b6d7004e3c3c9d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234055"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a>Фокус клавиатуры теперь правильно перемещается на нескольких слоях размещения WinForms и WPF

|   |   |
|---|---|
|Подробные сведения|Рассмотрим приложение WPF для размещения элемента управления WinForms, который, в свою очередь, содержит элементы управления WPF. Пользователи не могут перейти из слоя WinForms, если первый или последний элемент управления в этом слое является <code>System.Windows.Forms.Integration.ElementHost</code> WPF. Это изменение устраняет эту проблему: теперь пользователи могут выйти из слоя WinForms. Автоматические приложения, зависящие от фокуса, который никогда не должен выходить из слоя WinForms, могут перестать работать должным образом.|
|Предложение|Разработчики, желающие использовать это изменение в приложениях для целевой платформы .NET Framework 4.7.2 и более ранних версий, могут задать для следующего набора флагов AppContext значение false, чтобы включить изменение.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Для приложений WPF необходимо включить использование всех более ранних усовершенствований специальных возможностей для получения более поздних усовершенствований. Другими словами, оба переключателя, <code>Switch.UseLegacyAccessibilityFeatures</code> и <code>Switch.UseLegacyAccessibilityFeatures.2</code>, должны быть заданы. Разработчики, которым требуются прежние функции при нацеливании на .NET 4.7.2 и более поздних версий, могут установить для следующего флага AppContext значение true, чтобы отключить изменение.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|
