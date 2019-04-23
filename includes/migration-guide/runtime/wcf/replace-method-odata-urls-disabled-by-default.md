---
ms.openlocfilehash: 6dc3669433804a4524c18d5a932f9879343ab508
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804883"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>Метод Replace в URL-адресах OData по умолчанию отключен

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5, метод Replace в URL-адресах OData по умолчанию отключен. Если метод Replace OData отключен (теперь по умолчанию), все запросы пользователя, включая функции Replace (которые используются редко), завершатся ошибкой.|
|Предложение|Если необходим метод Replace (который используется редко), его можно включить в параметрах конфигурации (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>). Однако включенный метод Replace может открывать уязвимости системы безопасности, поэтому он должен использоваться только после тщательной проверки.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
