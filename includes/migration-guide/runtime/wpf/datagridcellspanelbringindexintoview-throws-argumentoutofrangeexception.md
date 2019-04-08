---
ms.openlocfilehash: e8fcd496b9c1921753ad0e1c2632f29bc5036956
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760701"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView создает исключение ArgumentOutOfRangeException

|   |   |
|---|---|
|Подробные сведения|Метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> будет выполняться асинхронно, если виртуализация столбцов включена, но ширина столбцов еще не определена.  Если столбцы удаляются до завершения асинхронной операции, может возникнуть исключение <xref:System.ArgumentOutOfRangeException?displayProperty=name>.|
|Предложение|Выполните одно из следующих действий:<ol><li>Выполните обновление до .NET Framework 4.7.</li><li>Установите последнее служебное исправление для .NET Framework 4.6.2.</li><li>Избегать удаления столбцов до завершения асинхронного ответа на метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</li></ol>|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|

