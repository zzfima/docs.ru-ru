---
ms.openlocfilehash: a51738fa75ba2dd4574549fce2570df8231c4cae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59234974"
---
### <a name="path-colon-checks-are-stricter"></a>Более строгие проверки двоеточий в пути

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.6.2 выполнен ряд изменений для поддержки ранее не поддерживаемых путей (по длине и формату). Исправлены проверки надлежащего синтаксиса разделителя диска (двоеточие), в результате появился побочный эффект в виде блокировки некоторых путей универсального кода ресурса (URI) в некоторых API-интерфейсах пути, где раньше это допускалось.|
|Предложение|При передаче универсального кода ресурса (URI) в соответствующий API сначала измените строку, чтобы она содержала допустимый путь.<ul><li>Удалите схему из URL-адресов вручную (например, удалите <code>file://</code> из URL-адресов)</li><li>Передайте универсальный код ресурса (URI) в класс <xref:System.Uri> и используйте <xref:System.Uri.LocalPath></li></ul>Кроме того, вы можете отказаться от новой нормализации путей, установив для переключателя <code>Switch.System.IO.UseLegacyPathHandling</code> AppContext значение true.|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType></li></ul>|
