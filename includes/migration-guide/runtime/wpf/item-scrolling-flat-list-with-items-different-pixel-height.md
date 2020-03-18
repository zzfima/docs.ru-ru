---
ms.openlocfilehash: 3a82822aae281ea7e873ba649f05b1d68686ec69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997704"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>Поэлементная прокрутка плоского списка с элементами, имеющими различную высоту в пикселях

|   |   |
|---|---|
|Подробнее|Когда <xref:System.Windows.Controls.ItemsControl?displayProperty=name> отображает коллекцию с помощью виртуализации (<code>IsVirtualizing=true</code>) и прокрутки элемента (<code>ScrollUnit=Item</code>) и когда элемент управления прокручивается для отображения элемента, высота которого в пикселях отличается о высоты соседних элементов, <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> выполняет итерацию по всем элементам в коллекции. Пользовательский интерфейс не отвечает на запросы в ходе этой итерации; если коллекция большая, это может восприниматься как зависание. Такая итерация происходит и в других ситуациях, даже в более ранних выпусках .NET Framework. Например, она происходит при пиксельной прокрутке (<code>ScrollUnit=Pixel</code>) при обнаружении элемента другой высоты в пикселях, а также при поэлементной прокрутке иерархических данных (например, в элементе управления <xref:System.Windows.Controls.TreeView?displayProperty=name> или <xref:System.Windows.Controls.ItemsControl?displayProperty=name> с включенным группированием) при обнаружении элемента, число подчиненных элементов которого отличается от соседних элементов. Для поэлементной прокрутки элементов с разной высотой в пикселях эта итерация была представлена в .NET Framework 4.6.1, чтобы устранить ошибки, связанные с макетом иерархических данных.  Итерация не требуется, если данные не структурированы (без иерархии), и в этом случае .NET Framework 4.6.2 не выполняет ее.|
|Предложение|Если итерация выполняется в .NET Framework 4.6.1, но не в более ранних выпусках, т. е. если <xref:System.Windows.Controls.ItemsControl?displayProperty=name> прокручивает поэлементно плоский список с элементами разной высоты в пикселях, то существует два решения:<ol><li>Установите .NET Framework 4.6.2.</li><li>Установите исправление HR 1605 для .NET Framework 4.6.1.</li></ol>|
|Область|Дополнительный номер|
|Version|4.6.1|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType></li></ul>|
