---
ms.openlocfilehash: f5d93d76ab3409d4d4c1870cfef94cac59f9475c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774065"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a>Метод PrivateFontCollection.AddFontFile освобождает ресурсы шрифтов

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7.1 и предыдущих версиях класс <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> не освобождает ресурсы шрифтов GDI + после того, как <xref:System.Drawing.Text.PrivateFontCollection> удаляется для объектов <xref:System.Drawing.Font>, добавляемых в эту коллекцию с помощью метода <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)>. В платформе .NET Framework 4.7.2 и более поздних версиях класс <xref:System.Drawing.Text.FontCollection.Dispose%2A> освобождает шрифты GDI+, которые были добавлены в коллекцию как файлы.|
|Предложение|<strong>Как принять или отклонить изменения</strong>Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:<ul><li>Выполнить повторную компиляцию, чтобы нацелить приложение на .NET Framework 4.7.2. Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.</li><li>Оно нацелено на .NET Framework 4.7.1 и более ранние версии платформы и позволяет отказаться от функций специальных возможностей предыдущих версий путем добавления [переключателя AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения и получения значения <code>false</code>, как показано в следующем примере.</li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>В приложениях, предназначенных для .NET Framework 4.7.2 или более поздней версии, где требуется сохранить предыдущие функции, можно выбрать отказ от освобождения шрифта, явно установив этот переключатель AppContext в значение <code>true</code>.|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType></li><li><xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType></li></ul>|
