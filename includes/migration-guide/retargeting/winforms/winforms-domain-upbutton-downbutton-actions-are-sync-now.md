---
ms.openlocfilehash: e73fe48467ede501bae0ddd9362d9d55b3ca998b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774049"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>Действия upbutton и downbutton домена WinForm теперь синхронизированы

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7.1 и предыдущих версиях действие <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> элемента управления <xref:System.Windows.Forms.DomainUpDown> игнорируется, если присутствует текст элемента управления, и разработчику приходится использовать действие <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> для элемента управления перед использованием действия <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. Начиная с .NET Framework 4.7.2 оба действия, <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> и <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>, работают независимо друг от друга в этом сценарии и остаются синхронизированными.|
|Предложение|Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:<ul><li>Выполнить повторную компиляцию, чтобы нацелить приложение на .NET Framework 4.7.2. Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.</li><li>Для отказа от функций прокрутки предыдущих версий [переключатель AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) добавляется в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения и получает значение <code>false</code>, как показано в следующем примере.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType></li><li><xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType></li></ul>|
