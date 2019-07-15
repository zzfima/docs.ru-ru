---
ms.openlocfilehash: d6c658f306dd4792e3cb5dbdc9471043ca95a071
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859197"
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

