---
ms.openlocfilehash: a51738fa75ba2dd4574549fce2570df8231c4cae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859248"
---
### <a name="path-colon-checks-are-stricter"></a>Более строгие проверки двоеточий в пути

|   |   |
|---|---|
|Подробнее|В .NET Framework 4.6.2 выполнен ряд изменений для поддержки ранее не поддерживаемых путей (по длине и формату). Исправлены проверки надлежащего синтаксиса разделителя диска (двоеточие), в результате появился побочный эффект в виде блокировки некоторых путей универсального кода ресурса (URI) в некоторых API-интерфейсах пути, где раньше это допускалось.|
|Предложение|При передаче универсального кода ресурса (URI) в соответствующий API сначала измените строку, чтобы она содержала допустимый путь.<ul><li>Удалите схему из URL-адресов вручную (например, удалите <code>file://</code> из URL-адресов)</li><li>Передайте универсальный код ресурса (URI) в класс <xref:System.Uri> и используйте <xref:System.Uri.LocalPath></li></ul>Кроме того, вы можете отказаться от новой нормализации путей, установив для переключателя <code>Switch.System.IO.UseLegacyPathHandling</code> AppContext значение true.|
|Область|Пограничный случай|
|Version|4.6.2|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType></li></ul>|
