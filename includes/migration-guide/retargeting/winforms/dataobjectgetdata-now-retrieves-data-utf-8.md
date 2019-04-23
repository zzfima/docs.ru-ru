---
ms.openlocfilehash: e39b4e85b47902babac7a22a93aa64c2f86ef01f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804949"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a>DataObject.GetData теперь получает данные в кодировке UTF-8

|   |   |
|---|---|
|Подробные сведения|В приложениях, предназначенных для .NET Framework 4 или выполняющихся в .NET Framework 4.5.1 или более ранних версий, <code>DataObject.GetData</code> получает HTML-данные в виде строки ASCII. В результате символы, не относящиеся к ASCII (т. е. символы с кодами ASCII больше 0x7F), представляются двумя случайными символами.<p/>Для приложений, предназначенных для NET Framework 4.5 и более поздней версии и выполняемых в .NET Framework 4.5.2, <code>DataObject.GetData</code> получает HTML-данные в формате UTF-8, который правильно представляет символы с кодами более 0x7F.|
|Предложение|Если реализован обходной путь для проблемы с кодировкой HTML-строк (например, явная кодировка HTML-строки, полученной из буфера обмена, путем ее передачи в метод <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name>), и выполняется изменение целевой платформы приложения с версии 4 на версию 4.5, этот обходной путь необходимо удалить. Если по какой-либо причине требуется старое поведение, для приложения можно выбрать целевую платформу .NET Framework 4.0.|
|Область|Пограничный случай|
|Версия|4.5.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
