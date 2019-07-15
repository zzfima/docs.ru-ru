---
ms.openlocfilehash: b5f12e648a82ebaba7d09b546e8aa2fc7cd82a37
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803210"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>Вызов метода DataGrid.CommitEdit из обработчика CellEditEnding удаляет фокус

|   |   |
|---|---|
|Подробные сведения|Вызов метода <xref:System.Windows.Controls.DataGrid.CommitEdit> из одного из обработчиков событий <xref:System.Windows.Controls.DataGrid?displayProperty=name> <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> приводит к потере фокуса для <xref:System.Windows.Controls.DataGrid?displayProperty=name>.|
|Предложение|Это ошибка исправлена в .NET Framework 4.5.2, поэтому ее можно избежать путем обновления .NET Framework. Кроме того, ее можно избежать, явным образом повторно выбрав <xref:System.Windows.Controls.DataGrid?displayProperty=name> после вызова <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|

