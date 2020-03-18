---
ms.openlocfilehash: cc6d96bd614ff015ae2125c0f1477e18a91a68f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802682"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Изменение режима высокой контрастности ComboBox svcTraceViewer

|   |   |
|---|---|
|Подробнее|В [программе Microsoft Service Trace Viewer](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) элементы управления ComboBox не отображались в правильном цвете в некоторых темах высокой контрастности. Проблема устранена в .NET Framework 4.7.2. Но из-за требований обратной совместимости пакета SDK для .NET Framework исправление не видно клиентам по умолчанию. .NET 4.8 предоставляет это изменение, добавив следующие [параметры конфигурации AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в файл конфигурации svcTraceViewer.exe.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Предложение|<ul><li>Как отказаться от изменения. Если вы не хотите менять поведение тем с высокой контрастностью, отключите его, удалив из файла svcTraceViewer.exe.config следующий раздел:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Version|4.8|
|Type|Параметры выполнения|
