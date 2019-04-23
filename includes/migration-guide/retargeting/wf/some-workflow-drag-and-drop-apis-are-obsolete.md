---
ms.openlocfilehash: 297af393e86c65e84ea7271d98eab36dbc6dbb0e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774480"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a>Некоторые API-интерфейсы перетаскивания в WorkFlow являются устаревшими

|   |   |
|---|---|
|Подробные сведения|Этот API перетаскивания рабочего процесса является устаревшим и будет вызывать предупреждения компилятора, если приложение перестроено на версии 4.5.|
|Предложение|Следует использовать новые API <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name>, которые поддерживают операции с несколькими объектами. Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версией компилятора. Интерфейсы API по-прежнему поддерживаются.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType></li></ul>|
