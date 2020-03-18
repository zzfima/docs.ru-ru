---
ms.openlocfilehash: 2f960942bda54505690cbac3151ef74ec0ab5ebb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235511"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>При использовании реентерабельных служб может возникнуть взаимоблокировка

|   |   |
|---|---|
|Подробнее|В реентерабельной службе может возникнуть взаимоблокировка, которая ограничивает экземпляры службы одним потоком выполнения за раз. Службы, в которых может возникнуть это проблема, имеют следующий <xref:System.ServiceModel.ServiceBehaviorAttribute> в коде:<pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]&#13;&#10;</code></pre>|
|Предложение|Чтобы устранить эту проблему, выполните следующие действия:<ul><li>Установите для режима параллелизма службы <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> или &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;. Пример:</li></ul><pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single)]&#13;&#10;</code></pre><ul><li>Установите последнее обновление для .NET Framework 4.6.2 или обновитесь до последней версии платформы .NET Framework. Это приведет к отключению потока <xref:System.Threading.ExecutionContext> в <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Это поведение можно настраивать. Это эквивалентно добавлению следующего параметра приложения в файл конфигурации:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Значение <code>Switch.System.ServiceModel.DisableOperationContextAsyncFlow</code> нельзя устанавливать на <code>false</code> для реентерабельных служб.|
|Область|Дополнительный номер|
|Version|4.6.2|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType></li></ul>|
