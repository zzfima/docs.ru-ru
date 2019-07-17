---
ms.openlocfilehash: a0dc2401155a162eaa5aa6b4d9e6af1ca1c2ccc8
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802638"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Улучшение производительности привязки данных для KeyedCollection

|   |   |
|---|---|
|Подробные сведения|Исправлено некорректное использование <xref:System.Windows.Data.Binding> индексатора IList, если исходный объект объявляет настраиваемый индексатор с такой же сигнатурой (например, KeyedCollection&lt;int,TItem&gt;).|
|Предложение|Чтобы приложение могло использовать это изменение, необходимо запустить его на платформе .NET Framework 4.7.2 или более поздней версии и включить это изменение, добавив следующий [параметр AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) в разделе <code>&lt;runtime&gt;</code> файла конфигурации приложения и установив для него значение <code>false</code>:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Значительно|
|Версия|4.8|
|Тип|Среда выполнения|

