---
ms.openlocfilehash: ac929a8b3e9a7d56122f5699c51819ad483d1f5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804934"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a>BinaryFormatter может не находить тип в контексте LoadFrom

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5 ряд изменений <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> может привести к различиям в десериализации при использовании <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> для десериализации типов, загруженных в контекст LoadFrom. Эти изменения связаны с тем, что <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> теперь иначе загружает тип. Это приводит к другому поведению, когда <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> пытается выполнить десериализацию в этот тип позднее. Модуль привязки сериализации по умолчанию не выполняет автоматический поиск контекста LoadFrom, хотя это могло работать в некоторых случаях при старом поведении XmlSerializer. В связи с изменениями, когда этот тип загружается из сборки, загруженной в другом контексте, может возникнуть исключение <xref:System.IO.FileNotFoundException?displayProperty=name>.|
|Предложение|Если это исключение возникает, в свойстве <code>Binder</code> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> можно задать пользовательский модуль привязки, который найдет правильный тип.<pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre>А затем пользовательский модуль привязки:<pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
