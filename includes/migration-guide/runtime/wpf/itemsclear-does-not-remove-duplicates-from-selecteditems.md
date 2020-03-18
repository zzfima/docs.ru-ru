---
ms.openlocfilehash: 1545c807e3bef675e63e14d01ab82c1131600f39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857531"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear не удаляет дубликаты из SelectedItems

|   |   |
|---|---|
|Подробнее|Если в элементе Selector, поддерживающем выбор нескольких элементов, в коллекции <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> присутствуют дубликаты, один и тот же элемент присутствует несколько раз.  Удаление этих элементов из источника данных (например, путем вызова Items.Clear) не приведет к их удалению из коллекции <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>. Будет удален только первый экземпляр. Более того, последующее использование коллекции <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>, например вызов SelectedItems.Clear(), может вызвать проблемы, например исключение <xref:System.ArgumentException?displayProperty=name>, так как коллекция <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> содержит элементы, которые отсутствуют в источнике данных.|
|Предложение|По возможности выполните обновление до .NET 4.6.2.|
|Область|Дополнительный номер|
|Version|4,5|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
