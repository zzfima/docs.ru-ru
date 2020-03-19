---
ms.openlocfilehash: e08b78b49cab88d4435d75b04bd446b413a61340
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859258"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>OperationContext.Current может возвращать значение NULL при вызове в конструкции Using

|   |   |
|---|---|
|Подробнее|<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> может возвращать <code>null</code> и создавать <xref:System.NullReferenceException>, если все следующие условия верны:<ul><li>Вы извлекаете значение свойства <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> в методе, который возвращает <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.</li><li>Вы создаете экземпляр объекта <xref:System.ServiceModel.OperationContextScope> в конструкции <code>using</code>.</li><li>Вы получаете значение свойства <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> в <code>using statement</code>. Пример:</li></ul><pre><code class="lang-csharp">using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext context = OperationContext.Current;      // OperationContext.Current is null.&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre>|
|Предложение|Чтобы устранить эту проблему, выполните следующие действия:<ul><li>Измените код таким образом, чтобы создавать экземпляр нового объекта, не являющегося <code>null</code> <xref:System.ServiceModel.OperationContext.Current%2A>:</li></ul><pre><code class="lang-csharp">OperationContext ocx = OperationContext.Current;&#13;&#10;using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext.Current = new OperationContext(ocx.Channel);&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre><ul><li>Установите последнее обновление для .NET Framework 4.6.2 или обновитесь до последней версии платформы .NET Framework. Это приведет к отключению потока <xref:System.Threading.ExecutionContext> в <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> и восстановлению поведения приложений WCF в .NET Framework 4.6.1 и более ранних версий. Это поведение можно настраивать. Это эквивалентно добавлению следующего параметра приложения в файл конфигурации:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Если это изменение нежелательно и приложение зависит от выполнения контекста при переходе между контекстами операции, этот поток можно включить следующим образом:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;false&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Version|4.6.2|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType></li></ul>|
