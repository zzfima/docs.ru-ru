---
ms.openlocfilehash: f1a1eab471d46f018a8e0d0cf787d487cf67c11e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234019"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>Свойство ContextMenuStrip.SourceControl содержит допустимый элемент управления при наличии вложенных объектов ToolStripMenuItem

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7.1 и предыдущих версиях свойство <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> некорректно возвращает значение null, когда пользователь открывает меню из вложенных элементов управления <xref:System.Windows.Forms.ToolStripMenuItem>. В платформе .NET Framework 4.7.2 и более поздних версий для свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> всегда задана фактическая система управления версиями.|
|Предложение|<strong>Как принять или отклонить изменения</strong>Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:<ul><li>Приложение предназначено для платформы .NET Framework 4.7.2. Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.</li><li>Оно нацелено на .NET Framework 4.7.1 и более ранние версии платформы и позволяет отказаться от функций специальных возможностей предыдущих версий путем добавления [переключателя AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения и получения значения <code>false</code>, как показано в следующем примере.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>В приложениях, предназначенных для .NET Framework 4.7.2 или более поздней версии, где требуется сохранить предыдущие функции, можно выбрать использование прежнего значения системы управления версиями, явно установив этот переключатель AppContext в значение <code>true</code>.|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType></li></ul>|
