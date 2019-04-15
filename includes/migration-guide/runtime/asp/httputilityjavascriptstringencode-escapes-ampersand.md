---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235928"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>Метод HttpUtility.JavaScriptStringEncode экранирует символ амперсанда

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.5, метод <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> экранирует символ амперсанда (&amp;).|
|Предложение|Если в приложении предполагается прежнее поведение данного метода, можно добавить параметр aspnet:JavaScriptDoNotEncodeAmpersand в [элемент appSettings ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) в файле конфигурации.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
