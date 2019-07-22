---
ms.openlocfilehash: d5ef5da90dd3fc39febf8e4cd4955b4113343976
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68235499"
---
### <a name="changes-in-path-normalization"></a>Изменения нормализации путей

|   |   |
|---|---|
|Подробные сведения|Начиная с приложений, предназначенных для .NET Framework 4.6.2, был изменен способ нормализации путей в среде выполнения. Нормализация пути включает в себя изменение строки, обозначающей путь или файл, чтобы эта строка соответствовала допустимому пути в целевой операционной системе. Нормализация обычно включает в себя:<ul><li>канонизацию разделителей компонентов и каталогов;</li><li>применение текущего каталога к относительному пути;</li><li>оценку относительного каталога (.) или родительского каталога (..) в пути;</li><li>обрезку указанных символов.</li></ul>Начиная с приложений, предназначенных для .NET Framework 4.6.2, следующие изменения в нормализации пути включены по умолчанию:<ul><li>Среда выполнения перекладывает нормализацию путей на функцию [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) операционной системы.</li><li>Нормализация больше не предусматривает обрезки окончания сегментов каталогов (например, пробела в конце имени каталога).</li><li>Поддержка синтаксиса пути устройства в режиме полного доверия, включая <code>\\.\</code> and, for file I/O APIs in mscorlib.dll, <code>\\?\</code>.</li><li>The runtime does not validate device syntax paths.</li><li>The use of device syntax to access alternate data streams is supported.</li></ul>These changes improve performance while allowing methods to access previously inaccessible paths. Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.|
|Предложение|В приложениях, предназначенных для .NET Framework 4.6.2 или более поздней версии, данное изменение можно отключить и использовать устаревшую нормализацию, добавив следующее в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>В приложениях, предназначенных для .NET Framework 4.6.1 или более ранней версии, но работающих на платформе .NET Framework 4.6.2 или более поздней версии, можно включить изменения в нормализацию пути, добавив следующее в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.UseLegacyPathHandling=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.6.2|
|Тип|Изменение целевой платформы|
