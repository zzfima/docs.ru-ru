---
ms.openlocfilehash: e39b4e85b47902babac7a22a93aa64c2f86ef01f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804647"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a>DataObject.GetData теперь получает данные в кодировке UTF-8

|   |   |
|---|---|
|Подробнее|В приложениях, предназначенных для .NET Framework 4 или выполняющихся в .NET Framework 4.5.1 или более ранних версий, <code>DataObject.GetData</code> получает HTML-данные в виде строки ASCII. В результате символы, не относящиеся к ASCII (т. е. символы с кодами ASCII больше 0x7F), представляются двумя случайными символами.<p/>Для приложений, предназначенных для NET Framework 4.5 и более поздней версии и выполняемых в .NET Framework 4.5.2, <code>DataObject.GetData</code> получает HTML-данные в формате UTF-8, который правильно представляет символы с кодами более 0x7F.|
|Предложение|Если реализован обходной путь для проблемы с кодировкой HTML-строк (например, явная кодировка HTML-строки, полученной из буфера обмена, путем ее передачи в метод <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name>), и выполняется изменение целевой платформы приложения с версии 4 на версию 4.5, этот обходной путь необходимо удалить. Если по какой-либо причине требуется старое поведение, для приложения можно выбрать целевую платформу .NET Framework 4.0.|
|Область|Пограничный случай|
|Version|4.5.2|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
