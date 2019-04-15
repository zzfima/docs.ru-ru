---
ms.openlocfilehash: e7154919d6a09a04e650d5546feb2ae6c6cc912f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234989"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath создает исключение NullReferenceException

|   |   |
|---|---|
|Подробные сведения|В платформе .NET Framework 4.6.2 среда выполнения создает исключение <code>T:System.NullReferenceException</code> при получении значения <code>P:System.Web.HttpRuntime.AppDomainAppPath</code>, которое содержит нуль-символы. В .NET Framework 4.6.1 и более ранних версий среда выполнения создает исключение <code>T:System.ArgumentNullException</code>.|
|Предложение|В ответ на это изменение можно выполнить одно из следующих действий:<ul><li>обрабатывайте <code>T:System.NullReferenceException</code>, если приложение работает на платформе .NET Framework 4.6.2;</li><li>обновите систему до версии .NET Framework 4.7, в которой восстановлено прежнее поведение, то есть создается исключение <code>T:System.ArgumentNullException</code>.</li></ul>|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|
